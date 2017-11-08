# Learn the Basics 

React Native is like React, but it uses native components instead of web components as building blocks. So to understand the basic structure of a React Native app, you need to understand some of the basic React concepts, like JSX, components, state, and props. If you already know React, you still need to learn some React-Native-specific stuff, like the native components. This tutorial is aimed at all audiences, whether you have React experience or not.

React Native は React と似ています。ただし、アプリケーションを構成するために、Web Component ではなく Native Component を用いる点は異なっています。ですので React Native App の基本的な概念を学ぶためには、React の基礎的な概念を理解する必要があります。例えば JSX, component, state, prop といった概念などです。React をすでに知っているのであれば、さらに進んで native component のような React Native に特有の概念を学んでいく必要があります。本チュートリアルは、React の経験がある人もない人も、全ての方向けに作成されています。

Let's do this thing.

では進めていきましょう。

## Hello World 

In accordance with the ancient traditions of our people, we must first build an app that does nothing except say "Hello world". Here it is:

太古からの我々の伝統に乗っ取り、「Hello, world」と言う以外に何もしないアプリケーションを構築しましょう。

```js
import React, { Component } from 'react';
import { Text } from 'react-native';

export default class HelloWorldApp extends Component {
  render() {
    return (
      <Text>Hello world!</Text>
    );
  }
}

```

If you are feeling curious, you can play around with sample code directly in the web simulators. You can also paste it into your App.js file to create a real app on your local machine.

興味があれば、サンプルコードを Web シミュレータ上で直接実行してみてください。もしくは上記のコードを App.js ファイルにペースとして、ローカルマシーン上の実際のアプリケーションの上で実行してみましょう。

## What's going on here?
何がおきているか

Some of the things in here might not look like JavaScript to you. Don't panic. This is the future.

ここで起きていることは、JavaScript のようには見えないかもしれません。動転しないでください。これは次世代の JavaScript なんです。

First of all, ES2015 (also known as ES6) is a set of improvements to JavaScript that is now part of the official standard, but not yet supported by all browsers, so often it isn't used yet in web development. React Native ships with ES2015 support, so you can use this stuff without worrying about compatibility. import, from, class, extends, and the () => syntax in the example above are all ES2015 features. If you aren't familiar with ES2015, you can probably pick it up just by reading through sample code like this tutorial has. If you want, [this page](https://babeljs.io/learn-es2015/) has a good overview of ES2015 features.

訳注：ES2015 についての解説。ES2015について慣れていない人は、[this page](https://babeljs.io/learn-es2015/)を参照。

The other unusual thing in this code example is `<Text>` Hello world!`</Text>`. This is JSX - a syntax for embedding XML within JavaScript. Many frameworks use a special templating language which lets you embed code inside markup language. In React, this is reversed. JSX lets you write your markup language inside code. It looks like HTML on the web, except instead of web things like `<div>` or `<span>`, you use React components. In this case, `<Text>` is a built-in component that just displays some text.

訳注：`<Text>` は見慣れない構文であるが、これはJSX の記法。React Compont の呼び出し。詳しくは React そのもののマニュアルを参照。

Components 
So this code is defining HelloWorldApp, a new Component. When you're building a React Native app, you'll be making new components a lot. Anything you see on the screen is some sort of component. A component can be pretty simple - the only thing that's required is a render function which returns some JSX to render.

This app doesn't do very much 
Good point. To make components do more interesting things, you need to learn about Props.