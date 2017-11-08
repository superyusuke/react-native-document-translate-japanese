# Props

Most components can be customized when they are created, with different parameters. These creation parameters are called props.

ほとんどのコンポーネントは、作成される際に、異なるパラメーターを元に、カスタマイズすることができます。この際に用いるパラメーターが、props です。

For example, one basic React Native component is the `Image`. When you create an `image`, you can use a prop named source to control what `image` it shows.

例えば、React Native コンポーネントの基礎的なものの一つして `Image` がありますが、この `Image` を作成する際に、source という名前の prop を用いることで `Image` コンポーネントが何を表示するかを制御することができます。

```js
import React, { Component } from 'react';
import { AppRegistry, Image } from 'react-native';

export default class Bananas extends Component {
  render() {
    let pic = {
      uri: 'https://upload.wikimedia.org/wikipedia/commons/d/de/Bananavarieties.jpg'
    };
    return (
      <Image source={pic} style={{width: 193, height: 110}}/>
    );
  }
}

// skip this line if using Create React Native App
// この行は Create React Native App を用いた場合には必要ありません。
AppRegistry.registerComponent('AwesomeProject', () => Bananas);
```

Notice that {pic} is surrounded by braces, to embed the variable `pic` into JSX. You can put any JavaScript expression inside braces in JSX.

{pic} というふうに、{} で囲まれている点に着目してください。これによって `pic` と言う変数を JSX の中に埋め込んでいます。JSX 内に {} によって、どんな JavaScript expression も埋め込むことができます。

Your own components can also use props. This lets you make a single component that is used in many different places in your app, with slightly different properties in each place. Just refer to this.props in your render function. Here's an example:

自分作成したコンポーネントにも props を用いることができます。これによって、同じコンポーネントを様々な場所で、少しだけ異なる内容を持たせて使用することが可能になります。Render function の中で、this.props を参照するだけです。

```js
import React, { Component } from 'react';
import { AppRegistry, Text, View } from 'react-native';

class Greeting extends Component {
  render() {
    return (
      <Text>Hello {this.props.name}!</Text>
    );
  }
}

export default class LotsOfGreetings extends Component {
  render() {
    return (
      <View style={{alignItems: 'center'}}>
        <Greeting name='Rexxar' />
        <Greeting name='Jaina' />
        <Greeting name='Valeera' />
      </View>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => LotsOfGreetings);
```

Using name as a prop lets us customize the Greeting component, so we can reuse that component for each of our greetings. This example also uses the Greeting component in JSX, just like the built-in components. The power to do this is what makes React so cool - if you find yourself wishing that you had a different set of UI primitives to work with, you just invent new ones.

name という prop を用いることで、Greeting コンポーネントをカスタマイズすることができるので、同じコンポーネントをそれぞれ異なる挨拶に対して使いまわすことができます。また、この例では Greeting コンポーネントを JSX の中で用いていますが、あたかも built-in コンポーネントかのように用いています。こうすることには大きな利点があり、それによって React   をとてもクールなものにしています。つまり、UI primitive(訳注：おそらく Native Cmponent のままの素朴な UI のこと) とは少し違ったものを使いたいと思った場合には、自分でそれを作ってしまえばいいのです。

The other new thing going on here is the View component. A View is useful as a container for other components, to help control style and layout.

ここではもう一つ新しいものが使われています。 View component です。View は、そのほかのコンポーネントのコンテイナーとして便利なもので、スタイルやレイアウトをコントロールする際に便利です。

With props and the basic Text, Image, and View components, you can build a wide variety of static screens. To learn how to make your app change over time, you need to learn about State.

props と 基礎的な `Text`, `Image`, `View` コンポンーネントによって、広範囲にわたる静的な画面を作り出すことができます。時間によって変化するアプリケーションを作りたい場合には、State を学ぶ必要があります。