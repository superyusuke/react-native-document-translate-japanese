# Getting Started

This page will help you install and build your first React Native app. If you already have React Native installed, you can skip ahead to the [Tutorial](http://facebook.github.io/react-native/releases/0.49/docs/tutorial.html).

このページは初めて React Native をインストールして、アプリケーションを作る人のための情報を提供します。すでにインストールしているひとは飛ばして、次のチュートリアルに進んでください。[(このチュートリアル)](http://facebook.github.io/react-native/releases/0.49/docs/tutorial.html)

## Quick Start

[Create React Native App](https://github.com/react-community/create-react-native-app) is the easiest way to start building a new React Native application. It allows you to start a project without installing or configuring any tools to build native code - no Xcode or Android Studio installation required \(see [Caveats](http://facebook.github.io/react-native/releases/0.49/docs/getting-started.html#caveats)\).

Create React App は、新規のリアクト・ネイティブ・アプリケーションを作るうえで一番簡単な方法です。native コードをビルドするために、他のツールのインストールや設定がまったく必要ありません。Xcode も Android Studio もインストールする必要がありません。

Assuming that you have [Node](https://nodejs.org/en/download/) installed, you can use npm to install the`create-react-native-app`command line utility:

ただし、Node がインストールされており、npm をつかってコマンドラインから create-react-app をインストールできる必要があります。

では次のコマンドでインストールしていきましょう。

```
$ npm install -g create-react-native-app
```

Then run the following commands to create a new React Native project called "AwesomeProject":

以下のコマンドで、"Awesome Project"という名称の新規の React Native プロジェクトを作成しましょう。

```
$ create-react-native-app AwesomeProject 
$ cd AwesomeProject
$ npm start
```

This will start a development server for you, and print a QR code in your terminal.

これで開発用サーバーが立ち上がり、QR コードがターミナルに表示されます。

## Running your React Native application

Install the[Expo](https://expo.io/) client app on your iOS or Android phone and connect to the same wireless network as your computer. Using the Expo app, scan the QR code from your terminal to open your project.

クライアントアプリケーションの [Expo](https://expo.io/) をご自身の iOS もしくは Android にインストールして、使用しているコンピューターと同じワイヤレスネットワークに接続してください。Expo アプリを使って ターミナルに表示された QR コードをスキャンをしましょう。するとプロジェクトが端末上で展開されます。

### Modifying your app

Now that you have successfully run the app, let's modify it. Open App.js in your text editor of choice and edit some lines. The application should reload automatically once you save your changes.

さてこれでアプリケーションを走らせることに成功しましたので、次は変更をくわえてきいきましょう。App.js をテキストエディターで開いて編集していきます。変更を加えると、自動的にアプリケーションがリロードされます。

### That's it!

Congratulations! You've successfully run and modified your first React Native app.

おめでとうございます。最初の React Native アプリを走らせて、さらに変更を加えることに成功しましたね。

## Now what?

次にどうすればいいか。

* Create React Native App also has a [user guide](https://github.com/react-community/create-react-native-app/blob/master/react-native-scripts/template/README.md)you can reference if you have questions specific to the tool.

* [User guide](https://github.com/react-community/create-react-native-app/blob/master/react-native-scripts/template/README.md)があるので、Create React Native Appに関して疑問があれば参照してください。


* If you can't get this to work, see the [Troubleshooting](https://github.com/react-community/create-react-native-app/blob/master/react-native-scripts/template/README.md#troubleshooting) section in the README for Create React Native App.

* うまくこのチュートリアルが動かなかった場合には、[Troubleshooting](https://github.com/react-community/create-react-native-app/blob/master/react-native-scripts/template/README.md#troubleshooting) を読んでください。

If you're curious to learn more about React Native, continue on to the [Tutorial](http://facebook.github.io/react-native/releases/0.49/docs/tutorial.html).

React Native について興味がうまれてもっと学びたいという場合には  [Tutorial](http://facebook.github.io/react-native/releases/0.49/docs/tutorial.html) を読み続けてください。

### Running your app on a simulator or virtual device

作成したアプリケーションを、シミュレータもしくは仮想デバイス上で動かす

Create React Native App makes it really easy to run your React Native app on a physical device without setting up a development environment. If you want to run your app on the iOS Simulator or an Android Virtual Device, please refer to the instructions for building projects with native code to learn how to install Xcode and set up your Android development environment.

Create React Native App は、開発環境の設定をする必要がないので非常に簡単に、実際の物理デバイス上でアプリケーションを走らせることができます。ですが、アプリケーションを iOS シミュレータや Android の仮想デバイス上で動かしたい場合には、Xcode のインストールと Android 開発環境のセットアップに関する説明を読んでください。

Once you've set these up, you can launch your app on an Android Virtual Device by running `npm run android`, or on the iOS Simulator by running `npm run ios` \(macOS only\).

セットアップが完了しさえすれば、Android Virtual Device の場合には  `npm run android`と実行すればアプリケーションをその上で動かすことができます。iOS シミュレータの場合には`npm run ios`と実行してください。(ただし iOS シミュレータは macOS でしか提供されていません)

### Caveats

Because you don't build any native code when using Create React Native App to create a project, it's not possible to include custom native modules beyond the React Native APIs and components that are available in the Expo client app.

If you know that you'll eventually need to include your own native code, Create React Native App is still a good way to get started. In that case you'll just need to "[eject](https://github.com/react-community/create-react-native-app/blob/master/react-native-scripts/template/README.md#ejecting-from-create-react-native-app)" eventually to create your own native builds. If you do eject, the "Building Projects with Native Code" instructions will be required to continue working on your project.

Create React Native App configures your project to use the most recent React Native version that is supported by the Expo client app. The Expo client app usually gains support for a given React Native version about a week after the React Native version is released as stable. You can check[this document](https://github.com/react-community/create-react-native-app/blob/master/VERSIONS.md)to find out what versions are supported.

If you're integrating React Native into an existing project, you'll want to skip Create React Native App and go directly to setting up the native build environment. Select "Building Projects with Native Code" above for instructions on configuring a native build environment for React Native.

