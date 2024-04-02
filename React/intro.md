# React - JS library for buidling UI's

ES6 - ECMAScript 6; standardizes JS

**class** - function that uses the keyword class to initialize 
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
  Note: The constructor function is called automatically when the object is initialized.

  - You can add your own methods to classes; call the method by referring to the object's method name followed by parentheses (parameters would go inside the parentheses):
```bash
  present() {
    return 'I have a ' + this.brand;
  }
}

mycar.present();
```
  - **class inheritance** - when one class inherits the class properties and methods to duplicate the behavior while allowing to add the extra features; uses `extend` keyword
   `super()` - method referring to the parent class; by calling it inside the `constructor()` method, we call the parent's `constructor()` method and get access to the parent's properties and methods.

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
You can pass parameters into (); **If you have only one parameter, you can skip them altogether**
`hello = (val) => "Hello " + val;` versus `hello = val => "Hello " + val;`
**there is no binding of `this` with arrow functions.**
  - in regular functions the `this` keyword refers to the object that called the function (e.g. `window`, `button`, etc.)
  - w/ arrow functions, the `this` keyword always represents the object that defined the arrow function.

**variables** - there are three ways of defining them: `var`, `let`, and `const`.
 VAR - function scope
  - var outside of a function - global scope.
  - var inside of a function - belongs to that function.
  - var inside of a block - still available outside of that block.
 LET - block scope
  - only available inside of the block (or expression) where it is defined.
 CONST - block scope
  - once created, its value can never change.
  - does not define a constant value, but a constant ***reference*** to a value.
  - you can't reassign constants, but you can: 
   - Change the elements of constant array
   - Change the properties of constant object

**array methods**
 - `map()` - runs a function on each item in the array and then returns a new array as the result; can generate lists

**destructuring** - extracts only what is needed.
- arrays
old way:
```bash
const vehicles = ['mustang', 'f-150', 'expedition'];

// old way
const car = vehicles[0];
const truck = vehicles[1];
const suv = vehicles[2];
```
new way:
```bash
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car, truck, suv] = vehicles;
```
  Note: When destructuring arrays, the order that variables are declared is important.

If we only want the car and suv we can simply leave out the truck but keep the comma:
```bash
const vehicles = ['mustang', 'f-150', 'expedition'];

const [car,, suv] = vehicles;
```
components - independent and resusable pieces of code
- function -
- class -

- render - 