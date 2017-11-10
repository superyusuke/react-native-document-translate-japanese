# Style

With React Native, you don't use a special language or syntax for defining styles. You just style your application using JavaScript. All of the core components accept a prop named style. The style names and values usually match how CSS works on the web, except names are written using camel casing, e.g backgroundColor rather than background-color.

React Native 使う場合、スタイルを定義するための、特別な言語やシンタックスは必要ありません。単に JavaScript を使ってアプリケーションをスタイリングしていきます。全てのコアとなるコンポーネントは、style という名前の prop を受け付けます。スタイルの名前とあたいはほとんど web で一般的に使われる CSS と同じですが、例外は名前がキャメルケースを使って書かれているものです。例えば backgroundColor とすべきで、background-color としてはいけません。

The style prop can be a plain old JavaScript object. That's the simplest and what we usually use for example code. You can also pass an array of styles - the last style in the array has precedence, so you can use this to inherit styles.

style prop は普通の伝統的な JavaScript のオブジェクトを渡します。これが一番シンプルな形式で、サンプルコードでは一般的にこのタイプが使われます。また style の配列を渡すこともできます。配列の最後のスタイルが適応されますので、これをつかってスタイルを継承させることができます。？

As a component grows in complexity, it is often cleaner to use StyleSheet.create to define several styles in one place. Here's an example: