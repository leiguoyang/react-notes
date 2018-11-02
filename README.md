# My understanding of React

React.js allow me to create component and place them on the webpage. Similarly, you create the electronic devices first, such as the capacitor, the diode, the resistor and then mount them to the circuit board.

A react component has two category of features:

- Mechanical structure, which is the html part. what you see on the screen.
- Electronic feature, which is the method part, such as the event listener and so on.

## Mechanical part
The `render()` method is used to create this part. What created is the React DOM, not the real DOM. I think this is the so-called virtual DOM.

```js
class ComponentName extends React.Component {
  render() {
      return <div>This is the returned element</div>;
  }
}
```

In the above example, it is to create a `div` element.

Moreover, you can display custom content on the element, like some text and data.

```js
class ComponentName extends React.Component {
  render() {
      return <div>{this.props.information}</div>;
  }
}
```

I wonder where the `props` comes from and confused. I think I can understand it better after better understand about JavaScript and the class syntax.

### Component composition
You can compose a component with other component, like am amplifier is made up of diodes and other electronic devices.

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
