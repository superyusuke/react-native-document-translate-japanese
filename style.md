# Style

With React Native, you don't use a special language or syntax for defining styles. You just style your application using JavaScript. All of the core components accept a prop named style. The style names and values usually match how CSS works on the web, except names are written using camel casing, e.g backgroundColor rather than background-color.

React Native 使う場合、スタイルを定義するための、特別な言語やシンタックスは必要ありません。単に JavaScript を使ってアプリケーションをスタイリングしていきます。全てのコアとなるコンポーネントは、style という名前の prop を受け付けます。スタイルの名前とあたいはほとんど web で一般的に使われる CSS と同じですが、例外は名前がキャメルケースを使って書かれているものです。例えば backgroundColor とすべきで、background-color としてはいけません。

The style prop can be a plain old JavaScript object. That's the simplest and what we usually use for example code. You can also pass an array of styles - the last style in the array has precedence, so you can use this to inherit styles.

style prop は普通の伝統的な JavaScript のオブジェクトを渡します。これが一番シンプルな形式で、サンプルコードでは一般的にこのタイプが使われます。また style の配列を渡すこともできます。配列の最後のスタイルが適応されますので、これをつかってスタイルを継承させることができます。(訳注：おそらく、配列の前から後ろへと上書きされていくということがいわれていると思われる。)

As a component grows in complexity, it is often cleaner to use StyleSheet.create to define several styles in one place. Here's an example:

コンポーネントが複雑になるにつれて、StyleSheet.create を用いて複数のスタイルを一箇所にまとめた方が、より綺麗に整頓できるはずです。次のように。

```js
import React, { Component } from 'react';
import { AppRegistry, StyleSheet, Text, View } from 'react-native';

export default class LotsOfStyles extends Component {
  render() {
    return (
      <View>
        <Text style={styles.red}>just red</Text>
        <Text style={styles.bigblue}>just bigblue</Text>
        <Text style={[styles.bigblue, styles.red]}>bigblue, then red</Text>
        <Text style={[styles.red, styles.bigblue]}>red, then bigblue</Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  bigblue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => LotsOfStyles);
```

One common pattern is to make your component accept a style prop which in turn is used to style subcomponents. You can use this to make styles "cascade" the way they do in CSS.

よくある手法として、コンポーネントには一つだけの style prop を受け取らせて、それを用いてサブコンポーネントをもスタイリングさせる手法です。これを用いて style を "cascade" することができます。これは CSS でも行われる手法ですね。(訳注：よくわからない。実例が欲しいところ。)

There are a lot more ways to customize text style. Check out the Text component reference for a complete list.

text のスタイリングをする方法はたくさんあります。Text component のリファレンスを参照してください。

Now you can make your text beautiful. The next step in becoming a style master is to learn how to control component size.

さあ Text を美しく装飾することができました。