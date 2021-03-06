# My understanding of React

## What is React
As the official statement from [https://reactjs.org/](https://reactjs.org/),

> A JavaScript library for building user interfaces

React.js allow me to create components and place them on the webpage. Similarly, you create the electronic devices first, such as the capacitor, the diode, the resistor and then mount them to the circuit board.

## Why use React
React have a good coding style of separation of apperance and behaviour when prototyping a component. It is natural.

## What is a component
A component is a functionally independant part of any system. So, if the component you create is unindependent, it is not a component at all. Therefore, you must make sure the component you design is independent.

**A component = Apperance + Behaviour**

- Apperance is the view, what you see on the screen, including the text, graphics, input controls, their dimension and style.
- Behaviour is the method.

For example, this example from React's homepage [https://reactjs.org/](https://reactjs.org/)

```js
class Timer extends React.Component {
  constructor(props) {
    super(props);
    this.state = { seconds: 0 };
  }

  tick() {
    this.setState(state => ({
      seconds: state.seconds + 1
    }));
  }

  componentDidMount() {
    this.interval = setInterval(() => this.tick(), 1000);
  }

  componentWillUnmount() {
    clearInterval(this.interval);
  }

  render() {
    return (
      <div>
        Seconds: {this.state.seconds}
      </div>
    );
  }
}

ReactDOM.render(<Timer />, mountNode);
```

The apperance is a `<div>` element showing the state.

```js
  <div>
    Seconds: {this.state.seconds}
  </div>
```

The method `tick`, `componentDidMount` and `componentWillUnmount` is Timer's behaviours.

In a component, you bind the apperance and behaviour via the event, such as the click event.

You use markup to define your apperance and JavaScript to define your behaviour, so you can have a good object-oriented thinking and coding style.

### Apperance

The `render()` method is used to create the apperance. What created is the React DOM, not the real DOM. I think this is the so-called virtual DOM.

```js
class ComponentName extends React.Component {
  render() {
      return <div>This is the returned element</div>;
  }
}
```

In the above example, it is to create a `<div>` element.

Moreover, you can display custom content on the element, like some text and data.

```js
class ComponentName extends React.Component {
  render() {
      return <div>{this.props.information}</div>;
  }
}
```

I wonder where the `props` comes from and confused. I think I can understand it better after better understand about JavaScript and the class syntax.

#### Component composition
You can compose a component with other components, like am amplifier is made up of diodes and other electronic devices.

```js
class ComponentName extends React.Component {
  render() {
      return (
      	<div
          <AnotherComponent />
          <AnotherComponent />     
        </div>
      );
  }
}
```

In this example, the `ComponentName` consists of two `AnotherComponent`s.

### Behaviour
