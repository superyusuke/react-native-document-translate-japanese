# React Native

Learn once, write anywhere: Build mobile apps with React

一度学べば、どんなところでもそれを書くことが出来る：モバイル・アプリケーションを React で構築する

Get Started

Learn the Basics

## ネイティブ・モバイル・アプリを JavaScript と React で構築する

_**Build native mobile apps using JavaScript and React**_

React Native lets you build mobile apps using only JavaScript. It uses the same design as React, letting you compose a rich mobile UI from declarative components.

React Native を用いることで、JavaScript だけでモバイル・アプリケーションを構築することができます。React Native は React と同じ構造を使用しており、宣言的に定義した Component を用いて、上質なモバイル UI を構成することができます。

```js
import React, { Component } from 'react';  
import { Text, View } from 'react-native';

class WhyReactNativeIsSoGreat extends Component {
  render() {
    return (
      <View>
        <Text>
          If you like React on the web, you'll like React Native.
        </Text>
        <Text>
          You just use native components like 'View' and 'Text',
          instead of web components like 'div' and 'span'.
        </Text>
      </View>
    );
  }
}
```

## React Native アプリは、本当の モバイル・アプリケーションです

_**A React Native app is a real mobile app**_

With React Native, you don't build a “mobile web app”, an “HTML5 app”, or a “hybrid app”. You build a real mobile app that's indistinguishable from an app built using Objective-C or Java. React Native uses the same fundamental UI building blocks as regular iOS and Android apps. You just put those building blocks together using JavaScript and React.

React Native で作成するのは「モバイル・ウェブ・アプリ」でも「HTML5 アプリ」でも「ハイブリッド・アプリ」でもありません。作成するのは、Objective-C や Java を用いて作成したアプリケーションと、未分けがつかない、本当のモバイル・アプリです。React Native は、通常の iOS や Android のアプリケーションと同じ基本的な UI ブロックを用います。これらの UI ブロックを JavaScript と React の中に組み込みます。

```js
import React, { Component } from 'react';
import { Image, ScrollView, Text } from 'react-native';

class AwkwardScrollingImageWithText extends Component {
  render() {
    return (
      <ScrollView>
        <Image
          source={{uri: 'https://i.chzbgr.com/full/7345954048/h7E2C65F9/'}}
          style={{width: 320, height:180}}
        />
        <Text>
          On iOS, a React Native ScrollView uses a native UIScrollView.
          On Android, it uses a native ScrollView.

          On iOS, a React Native Image uses a native UIImageView.
          On Android, it uses a native ImageView.

          React Native wraps the fundamental native components, giving you
          the performance of a native app, plus the clean design of React.
        </Text>
      </ScrollView>
    );
  }
}
```

## 再コンパイルに時間を浪費するのはやめにしましょう

_**Don't waste time recompiling**_

React Native lets you build your app faster. Instead of recompiling, you can reload your app instantly. With Hot Reloading, you can even run new code while retaining your application state. Give it a try - it's a magical experience.

React Native を使えば、以前より早くアプリを構築することができます。React Native では、再コンパイルをするのではなく、アプリケーションを即リロードさせることができます。[Hot Reloading](https://facebook.github.io/react-native/blog/2016/03/24/introducing-hot-reloading.html) によって、変更を加えた新しいコードを、アプリケーションの状態を保持したまま、実行することができます。試してみてください。魔法のような体験です。

![](https://media.giphy.com/media/13WZniThXy0hSE/giphy.gif)

## 必要な時にネイティブ・コードを使用することもできます

Use native code when you need to

React Native combines smoothly with components written in Objective-C, Java, or Swift. It's simple to drop down to native code if you need to optimize a few aspects of your application. It's also easy to build part of your app in React Native, and part of your app using native code directly - that's how the Facebook app works.

React Native はスムーズに、Objective-C や Java や Swift で書かれたコンポーネントを取り込むことができます。アプリのいくつかの側面を最適化するために、ネイティブ・コードを使用する方法は非常に簡潔です。またアプリの一部に React Native を用い、一部にネイティブ・コードを直に使うことも簡単です。Facebook アプリケーションもそのようにして動作しています。

```js
import React, { Component } from 'react';
import { Text, View } from 'react-native';
import { TheGreatestComponentInTheWorld } from './your-native-code';

class SomethingFast extends Component {
  render() {
    return (
      <View>
        <TheGreatestComponentInTheWorld />
        <Text>
          TheGreatestComponentInTheWorld could use native Objective-C,
          Java, or Swift - the product development process is the same.
        </Text>
      </View>
    );
  }
}
```

## React Native を始めましょう

Get Started with React Native

## Who's using React Native?

Thousands of apps are using React Native, from established Fortune 500 companies to hot new startups. If you're curious to see what can be accomplished with React Native, check out these apps!

何千ものアプリケーションが React Native を使用しています。その範囲は広く、既に評価が安定した Fortune 500 カンパニーから、今まさに動いている新規スタートアップでも使用されています。

More React Native apps

