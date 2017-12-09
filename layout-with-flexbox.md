# Layout with Flexbox

A component can specify the layout of its children using the flexbox algorithm. Flexbox is designed to provide a consistent layout on different screen sizes.

コンポーネントは、その子要素のレイアウトを、felxbox アルゴリズムを使って指定することができます。Flexbox はサイズの異なる様々なスクリーン上で一貫したレイアウトをデザインするために用いられます。

You will normally use a combination of `flexDirection`, `alignItems`, and `justifyContent` to achieve the right layout.

通常は `flexDirection`, `alignItems`, `justifyContent` を組み合わせて、希望するレイアウトを構成していることかと思います。

Flexbox works the same way in React Native as it does in CSS on the web, with a few exceptions. The defaults are different, with flexDirection defaulting to column instead of row, and the flex parameter only supporting a single number.

Flexbox は React Native においても、一部例外はあるものの、ウェブ上の CSS と同じように動作します。例えば default の flexDirection が異なり、React Native においては column がデフォルトの値になっています。また、flex が取れる値は単一の数字だけです。

## Flex Direction

Adding `flexDirection` to a component's `style` determines the **primary axis** of its layout. Should the children be organized horizontally (row) or vertically (column)? The default is column.

`flexDirection` をコンポーネントの `style` に与えることで、レイアウトの方向の主軸を決定します。(訳注: 水平方向か垂直方向かどちらに並べるかを決定するということ) 子要素が水平(row)もしくは垂直(column)に整列しましたか？デフォルトでは column が設定されています。

```js
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

export default class FlexDirectionBasics extends Component {
  render() {
    return (
      // Try setting `flexDirection` to `column`.
      // `flexDirection` を column にも変更してみましょう
      <View style={{flex: 1, flexDirection: 'row'}}>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
};

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => FlexDirectionBasics);
```

## Justify Content 

Adding `justifyContent` to a component's `style` determines the **distribution** of children along the `primary axis`. Should children be distributed at the start, the center, the end, or spaced evenly? Available options are `flex-start`, `center`, `flex-end`, `space-around`, and `space-between`.

`justifyContent` をコンポーネントの `style` に追加することで、子要素が主軸にそってどのような配分で配置されるかを規定します。 その配置は、始点に寄せる、中央寄せ、終点寄せ、もしくは均等揃えです。`justifyContent` のオプションは次の通りです。 `flex-start`, `center`, `flex-end`, `space-around`, and `space-between`.

```js
import React, { Component } from 'react';
import { AppRegistry, View } from 'react-native';

export default class JustifyContentBasics extends Component {
  render() {
    return (
      // Try setting `justifyContent` to `center`.
      // Try setting `flexDirection` to `row`.
      <View style={{
        flex: 1,
        flexDirection: 'column',
        justifyContent: 'space-between',
      }}>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'skyblue'}} />
        <View style={{width: 50, height: 50, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
};

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => JustifyContentBasics);

```

## Align Items
Adding alignItems to a component's style determines the alignment of children along the secondary axis (if the primary axis is row, then the secondary is column, and vice versa). Should children be aligned at the start, the center, the end, or stretched to fill? Available options are flex-start, center, flex-end, and stretch.










