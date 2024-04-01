# state - a component's "memory;" a React object that stores its property values

To update a component with new data (aka change its **state**):

1. **Retain** the data between renders.
2. **Trigger** React to render the component with new data.

## hook - allows function to access React features; only available *while* React is rendering
- always start with the word "use"
- can only be called at the top level of components or hooks

`useState` - React hook that lets you add a state variable to your component; used when you want your component to "remember" something:

`const [state, setState] = useState(initialState)`

  - creates a **state variable** that'll retain data between renders (`state`)
  - provides a **state setter function** to update the variable and trigger React to render the component again (`setState`)
  - The `[]` signifies **array destructuring**, which lets you read values from an array. 
  - The array returned by `useState` always has exactly two items.
  