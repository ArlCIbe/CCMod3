# ECMAScript 6 - standardizes JS

**class** - function that uses the keyword `class` to initialize 
  - properties are assigned inside a `constructor()` method
  - class names are capitalized

```bash
class Car {
  constructor(name) {
    this.brand = name;
  }
}

const mycar = new Car("Ford");
```
**Note:** The constructor function is called automatically when the object is initialized.

  - You can add your own methods to classes; call the `method()` by referring to the object's method name followed by parentheses (parameters would go inside the parentheses):
```bash
  present() {
    return 'I have a ' + this.brand;
  }
}

mycar.present();
```
  - **class inheritance** - when one class inherits the class properties and methods to duplicate the behavior while allowing to add the extra features; uses `extend` keyword

    - `super()` - method referring to the parent class; by calling it inside the `constructor()` method, we call the parent's `constructor()` method and get access to the parent's properties and methods.

```bash
class Model extends Car {
  constructor(name, mod) {
    super(name);
    this.model = mod;
  }  
  show() {
      return this.present() + ', it is a ' + this.model
  }
}

mycar.show();
```
**arrow functions** - shortened function syntax
```bash
hello = function() {
  return "Hello World!";
}
```
```bash
hello = () => {
  return "Hello World!";
}
```
**If there's only ONE statement AND the statement returns a value, you can use the following:**
`hello = () => "Hello World!";`

You can pass parameters into (); **If you have only one parameter, you can skip them altogether:**<br>
`hello = (val) => "Hello " + val;`

versus

`hello = val => "Hello " + val;`

**there is no binding of `this` with arrow functions.**
  - in regular functions the `this` keyword refers to the object that called the function (e.g. `window`, `button`, etc.)
  - w/ arrow functions, the `this` keyword always represents the object that defined the arrow function.

**variables** - there are three ways of defining them: `var`, `let`, and `const`.
 `var` - function scope<br>
  - var outside of a function - global scope.
  - var inside of a function - belongs to that function.
  - var inside of a block - still available outside of that block.
 `let` - block scope<br>
  - only available inside of the block (or expression) where it is defined.
 `const` - block scope<br>
  - once created, its value can never change.
  - does not define a constant value, but a constant ***reference*** to a value.
  - you can't reassign constants, but you can: 
   - Change the elements of constant array
   - Change the properties of constant object

**array methods**
 - `map()` - runs a function on each item in the array and then returns a new array as the result; can generate lists

**destructuring** - extracts only what is needed.

- arrays

 old way of assigning array items to a variable:
```bash
const vehicles = ['mustang', 'f-150', 'expedition'];

// old way
const car = vehicles[0];
const truck = vehicles[1];
const suv = vehicles[2];
```
new way (w/ destructuring):
```bash
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car, truck, suv] = vehicles;
```
**Note:** When destructuring arrays, the order that variables are declared is important.

If we only want the car and suv we can simply leave out the truck but keep the comma:
```bash
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car,, suv] = vehicles;
```
- objects

 old way of using an object inside a function:
```bash
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red'
}

myVehicle(vehicleOne);

// old way
function myVehicle(vehicle) {
  const message = 'My ' + vehicle.type + ' is a ' + vehicle.color + ' ' + vehicle.brand + ' ' + vehicle.model + '.';
}
```
new way (w/ destructuring):
```bash
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red'
}

myVehicle(vehicleOne);

function myVehicle({type, color, brand, model}) {
  const message = 'My ' + type + ' is a ' + color + ' ' + brand + ' ' + model + '.';
}
```
destructure deeply nested objects by referencing the nested object, then using a colon followed by {}:
```bash
const vehicleOne = {
  brand: 'Ford',
  model: 'Mustang',
  type: 'car',
  year: 2021, 
  color: 'red',
  registration: {
    city: 'Houston',
    state: 'Texas',
    country: 'USA'
  }
}

myVehicle(vehicleOne)

function myVehicle({ model, registration: { state } }) {
  const message = 'My ' + model + ' is registered in ' + state + '.';
}
```

**spread operator `(...)`** - allows us to quickly copy all or part of an existing array or object into another array or object.
```bash
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];
const numbersCombined = [...numbersOne, ...numbersTwo];
```
often used in combo with destructuring
```bash
const numbers = [1, 2, 3, 4, 5, 6];

const [one, two, ...rest] = numbers;
```
can be used with objects
```bash
const myVehicle = {
  brand: 'Ford',
  model: 'Mustang',
  color: 'red'
}

const updateMyVehicle = {
  type: 'car',
  year: 2021, 
  color: 'yellow'
}

const myUpdatedVehicle = {...myVehicle, ...updateMyVehicle}
```
console result:

Object *i*<br> 
```text
brand: "Ford"
color: "yellow"
model: "Mustang"
type: "car"
year: 2021
```
**Note:** Notice the properties that did not match were "combined", but the property that did match, `color`, was overwritten by the last object that was passed, `updateMyVehicle`. The resulting color is now yellow.

**Modules** - allow you to break your code up into separate files; relies on `import` and `export` statements

`export` 

named

- in-line individually
```bash
  export const name = "Jesse"
  export const age = 40
```

- all at once at the bottom
```bash
const name = "Jesse"
const age = 40

export { name, age }
```

default

```bash
const message = () => {
  const name = "Jesse";
  const age = 40;
  return name + ' is ' + age + 'years old.';
};

export default message;
```
**Note:** only one `default export` can exist in a file

`import`

- named exports

`import { name, age } from "./person.js";`

- default exports

`import message from "./message.js";`

**ternary operator `?`** - simplified conditional operator like if / else

syntax: `condition ? <expression if true> : <expression if false>`

traditional if/else statement:
```bash
if (authenticated) {
  renderApp();
} else {
  renderLogin();
}
```
same statement using ternary operator:

`authenticated ? renderApp() : renderLogin();`