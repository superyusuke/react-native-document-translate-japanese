# Height and Width

A component's height and width determine its size on the screen.

コンポーネントの高さと幅の定義によって、スクリーン上に表示されるサイズを規定します。

## Fixed Dimensions 

固定サイズの場合

The simplest way to set the dimensions of a component is by adding a fixed width and height to style. All dimensions in React Native are unitless, and represent density-independent pixels.

コンポーネントの縦横幅を決める一番簡単な方法は、style で幅と高さを与えることです。React Native に置ける全ての縦横幅は、untiless で、density-independent pixel を表しています。(訳注：1px がどのような規格基準での 1px なのかを表していると思われる)

```
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

export default class FixedDimensionsBasics extends Component {
  render() {
    return (
      <View>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 100, height: 100, backgroundColor: 'skyblue'}} />
        <View style={{width: 150, height: 150, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => FixedDimensionsBasics);
```

Setting dimensions this way is common for components that should always render at exactly the same size, regardless of screen dimensions.

このような方法で縦横幅を設定する方法は、いつでも同じサイズでレンダリングされるべきコンポーネントのために一般的に使われます。スクリーンのサイズがどうであれ一定幅でレンダリングする場合です。

# Flex Dimensions 

状況に合わせて伸縮する縦横幅

Use flex in a component's style to have the component expand and shrink dynamically based on available space. Normally you will use flex: 1, which tells a component to fill all available space, shared evenly amongst each other component with the same parent. The larger the flex given, the higher the ratio of space a component will take compared to its siblings.

コンポーネントの Style の中で flex を用いることで、使用可能なスペースに合わせて伸び縮みさせることができます。flex: 1 を用いると、コンポーネントに対して使えるスペース全部を埋めるように支持することになります。ただしその際に同じ親コンポーネントを持つ隣接するコンポーネントとその領域をわけあうことになります。flex の値が大きくなるほど、兄弟要素の間で、占める割合が増すことになります。


_A component can only expand to fill available space if its parent has dimensions greater than 0. If a parent does not have either a fixed width and height or flex, the parent will have dimensions of 0 and the flex children will not be visible.
_

コンポーネントは使用可能なスペース全てを埋めるわけですが、それは親要素の縦横幅が 0 以上の場合に限られます。もし親要素に高さや幅を固定もしくは flex で指定されてない場合、親要素の縦横幅が 0 になってしまうので、その子要素に flex が指定されていたとしても、見えなくなってしまいます。

```js
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

export default class FlexDimensionsBasics extends Component {
  render() {
    return (
      // Try removing the `flex: 1` on the parent View.
      // The parent will not have dimensions, so the children can't expand.
      // What if you add `height: 300` instead of `flex: 1`?

      <View style={{flex: 1}}>
        <View style={{flex: 2, backgroundColor: 'powderblue'}} />
        <View style={{flex: 2, backgroundColor: 'skyblue'}} />
        <View style={{flex: 3, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => FlexDimensionsBasics);
```

