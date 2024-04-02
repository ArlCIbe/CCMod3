# JSX

- expressions are written inside { }.
```bash
const myElement = <h1>React is {5 + 5} times better with JSX</h1>;
```

- to write HTML on multiple lines, put the HTML inside ():

```bash
const myElement = (
  <ul>
    <li>Apples</li>
    <li>Bananas</li>
    <li>Cherries</li>
  </ul>
);
```

- HTML code must be wrapped in ONE top level element.<br> 
JSX will throw an error if:
  - the HTML is not correct
  - the HTML misses a parent element.
```bash
const myElement = (
  <div>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </div>
);
```

- Alternatively, you can use a "fragment" (`<>  </>`) to wrap multiple lines which will prevent adding unnecessary nodes to the DOM.
```bash
const myElement = (
  <>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </>
);
```

- HTML elements must be properly closed; JSX will throw an error if not.

`const myElement = <input type="text" />;`

- since `class` is a reserved word in JS, you must use the attribute `className` instead. JSX translates `className` attributes into `class` attributes when it's rendered.

```bash
const myElement = <h1 className="myclass">Hello World</h1>;
```

- React supports if statements, but not inside JSX; you can either:

put the if statements outside of the JSX

```bash
const x = 5;
let text = "Goodbye";
if (x < 10) {
  text = "Hello";
}

const myElement = <h1>{text}</h1>;
```

use ternary expressions

```bash
const x = 5;

const myElement = <h1>{(x) < 10 ? "Hello" : "Goodbye"}</h1>;
```
**Note:** in order to embed a JS expression inside JSX, it must be wrapped with { }