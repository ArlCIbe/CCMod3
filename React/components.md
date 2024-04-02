# components - independent and reusable bits of code; functions that return HTML elements
name must start with a capital letter

`class` - must include the `extends React.Component` statement which creates an inheritance to `React.Component` and gives your component access to React.Component's functions; requires a `render()` method.
```bash
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```

`function` - behaves much the same way as a `class` component, but can be written using much less code
```bash
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```

- to use the `Car` component in your application, use similar syntax as normal HTML: <Car />
```bash
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

`props` (aka properties) - arguments passed into React components as HTML attributes (components themselves can also be passed as props)

- To send props into a component, use the same syntax as HTML attributes

`const myElement = <Car brand="Ford" />;`

- The component receives the argument as a props object:
```bash
function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}
```

to pass data from one component to another:
```bash
function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
to pass a variable from one component to another, put its name inside { }:
```bash
function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

function Garage() {
  const carName = "Ford";
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand={ carName } />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
to pass an object from one component to another:
```bash
function Car(props) {
  return <h2>I am a { props.brand.model }!</h2>;
}

function Garage() {
  const carInfo = { name: "Ford", model: "Mustang" };
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand={ carInfo } />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
**NOTE: React props are read-only; you'll get an error if you try to change their value.**
```

to refer to components inside other components:
```bash
function Car() {
  return <h2>I am a Car!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my Garage?</h1>
      <Car />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

to split components into separate files, create a new file with a .js file extension and put the code inside it:
```bash
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}

export default Car;
```

to be able to use the Car component, import the file in your application.
```bash
import React from 'react';
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```