# Layout with Flexbox 
A component can specify the layout of its children using the flexbox algorithm. Flexbox is designed to provide a consistent layout on different screen sizes.

You will normally use a combination of flexDirection, alignItems, and justifyContent to achieve the right layout.

Flexbox works the same way in React Native as it does in CSS on the web, with a few exceptions. The defaults are different, with flexDirection defaulting to column instead of row, and the flex parameter only supporting a single number.
Flex Direction 

Adding flexDirection to a component's style determines the primary axis of its layout. Should the children be organized horizontally (row) or vertically (column)? The default is column.

