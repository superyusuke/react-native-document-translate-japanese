# State

There are two types of data that control a component: props and state. props are set by the parent and they are fixed throughout the lifetime of a component. For data that is going to change, we have to use state.

コンピポーネントをコントロールするために用いることができるデータには、二種類あります。一つは prop で もう一つは state です。props は親要素から渡され、コンポーネントのライフタイムを通して固定されます。変化するデータに関しては、state を使う方が良いでしょう。

In general, you should initialize state in the constructor, and then call setState when you want to change it.

一般的に言って、コンストラクタにおいて state を初期化し、それを変える場合には setState を用います。

For example, let's say we want to make text that blinks all the time. The text itself gets set once when the blinking component gets created, so the text itself is a prop. The "whether the text is currently on or off" changes over time, so that should be kept in state.

例えば、テキストを時間経過にあわせて点滅させたいとします。テキスト自体は Blink コンポーネントが生成された際にコンポーネント自体に与えられ保持します。その際には prop 経由でテキストの内容を与えられます。

```js
import React, { Component } from 'react';
import { AppRegistry, Text, View } from 'react-native';

class Blink extends Component {
  constructor(props) {
    super(props);
    this.state = {showText: true};

    // Toggle the state every second
    setInterval(() => {
      this.setState(previousState => {
        return { showText: !previousState.showText };
      });
    }, 1000);
  }

  render() {
    let display = this.state.showText ? this.props.text : ' ';
    return (
      <Text>{display}</Text>
    );
  }
}

export default class BlinkApp extends Component {
  render() {
    return (
      <View>
        <Blink text='I love to blink' />
        <Blink text='Yes blinking is so great' />
        <Blink text='Why did they ever take this out of HTML' />
        <Blink text='Look at me look at me look at me' />
      </View>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => BlinkApp);
```

In a real application, you probably won't be setting state with a timer. You might set state when you have new data arrive from the server, or from user input. You can also use a state container like Redux to control your data flow. In that case you would use Redux to modify your state rather than calling setState directly.

実際のアプリケーションの場合には、state をタイマーを使ってセットするようなことはないでしょう。どちらかといえば、サーバーから新しいデータを取得した際や、ユーザーがインプットした際に、状態を変更するはずです。また Redux のような state container を用いて、data flow をコントロールすることもできます。その場合には Redux を使って状態を変更することになるので、setState をそのまま呼び出すことはありません。

When setState is called, BlinkApp will re-render its Component. By calling setState within the Timer, the component will re-render every time the Timer ticks.

State works the same way as it does in React, so for more details on handling state, you can look at the React.Component API. At this point, you might be annoyed that most of our examples so far use boring default black text. To make things more beautiful, you will have to learn about Style.