# State

There are two types of data that control a component: props and state. props are set by the parent and they are fixed throughout the lifetime of a component. For data that is going to change, we have to use state.

```
import React, { Component } from 'react';
import { AppRegistry, Text, View } from 'react-native';

class Blink extends Component {
  constructor(props) {
    super(props);
    this.state = {showText: true};

    // Toggle the state every second
    setInterval(() => {
      this.setState(previousState => {
        return { showText: !previousState.showText };
      });
    }, 1000);
  }

  render() {
    let display = this.state.showText ? this.props.text : ' ';
    return (
      <Text>{display}</Text>
    );
  }
}

export default class BlinkApp extends Component {
  render() {
    return (
      <View>
        <Blink text='I love to blink' />
        <Blink text='Yes blinking is so great' />
        <Blink text='Why did they ever take this out of HTML' />
        <Blink text='Look at me look at me look at me' />
      </View>
    );
  }
}
```

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => BlinkApp);

In general, you should initialize state in the constructor, and then call setState when you want to change it.

For example, let's say we want to make text that blinks all the time. The text itself gets set once when the blinking component gets created, so the text itself is a prop. The "whether the text is currently on or off" changes over time, so that should be kept in state.