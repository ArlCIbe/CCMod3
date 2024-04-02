# React - JS library for building user interfaces; renders HTML directly to a webpage

React renders HTML to the web page by using a function called cSBcreateRoot() and its method render().

`createRoot()` - function used by React to define the HTML element where a React componet should be displayed; takes only one argument (an HTML element)

`render()` - defines the React component that should be displayed on the UI; the React app will render in the div inside of the index.html file located in the public folder

```bash
const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(<p>Hello</p>);
```
The result is displayed in the `<div id="root">` element:
```bash
<body>
  <div id="root"></div>
</body
```

**JSX** - converts HTML tags into React elements
- allows you to write HTML tags directly inside of JS code
- places them in the DOM without using `createElement()`  and/or `appendChild()`
```bash
const myelement = (
  <table>
    <tr>
      <th>Name</th>
    </tr>
    <tr>
      <td>John</td>
    </tr>
    <tr>
      <td>Elsa</td>
    </tr>
  </table>
);

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(myelement);
```

**root node** - the HTML element where you want to display the result; a container for content managed by React (doesn't have to be a `<div>` or have the `id='root'`)
```bash
<body>

  <header id="sandy"></header>

</body>
```
Display the result in the `<header id="sandy">` element:
```bash
const container = document.getElementById('sandy');
const root = ReactDOM.createRoot(container);
root.render(<p>Hallo</p>);
```