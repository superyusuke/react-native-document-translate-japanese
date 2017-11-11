# Layout with Flexbox
A component can specify the layout of its children using the flexbox algorithm. Flexbox is designed to provide a consistent layout on different screen sizes.

コンポーネントは、その子要素のレイアウトを、felxbox アルゴリズムを使って指定することができます。Flexbox はサイズの異なる様々なスクリーン上で一貫したレイアウトをデザインするために用いられます。

You will normally use a combination of `flexDirection`, `alignItems`, and `justifyContent` to achieve the right layout.

通常は `flexDirection`, `alignItems`, `justifyContent` を組み合わせて、希望するレイアウトを構成していることかと思います。

Flexbox works the same way in React Native as it does in CSS on the web, with a few exceptions. The defaults are different, with flexDirection defaulting to column instead of row, and the flex parameter only supporting a single number.

Flexbox は React Native においても、一部例外はあるものの、ウェブ上の CSS と同じように動作します。例えば default の flexDirection が異なり、React Native においては column がデフォルトの値になっています。また、flex が取れる値は単一の数字だけです。

## Flex Direction 

Adding flexDirection to a component's style determines the primary axis of its layout. Should the children be organized horizontally (row) or vertically (column)? The default is column.

