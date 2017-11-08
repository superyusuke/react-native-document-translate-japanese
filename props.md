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