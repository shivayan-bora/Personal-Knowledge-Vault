---
id: qp0uwf7dogj9emc6zjq0mh5
title: Global State
desc: ''
updated: 1654590140188
created: 1654587336249
---
 
 Sometimes composition doesn't work for us. For that, we can use the context API (Note: [Before you use Context](https://reactjs.org/docs/context.html#before-you-use-context)):

  ```jsx
 const CounterContext = React.createContext()
 
 function Counter() {
  const {count, increment} = React.useContext(CounterContext);
  return <button onClick={increment}>{count}</button>
 }

 function CounterDisplay({count}) {
  const {count} = React.useContext(CounterContext);
  return <div>The current counter count is {count}</div>
 }

 function App() {
  const [count, setCount] = React.useState(0)
  const increment = () => setCount(c => c + 1)
  return <div>
   <CounterContext.Provider value={{count, increment}}>
    <CounterDisplay />
    <Counter />
   </CounterContext.Provider>
  </div>
 }
```

We can use `useReducer` hook along with it rather than `useState` as well:

```jsx
function countReducer(state, action) {
  switch (action.type) {
    case 'INCREMENT': {
      return {count: state.count + 1}
    }
    default: {
      throw new Error(`Unsupported action type: ${action.type}`)
    }
  }
}

function CountProvider(props) {
  const [state, dispatch] = React.useReducer(countReducer, {count: 0})
  const value = React.useMemo(() => [state, dispatch], [state])
  return <CountContext.Provider value={value} {...props} />
}

function useCount() {
  const context = React.useContext(CountContext)
  if (!context) {
    throw new Error(`useCount must be used within a CountProvider`)
  }
  const [state, dispatch] = context

  const increment = () => dispatch({type: 'INCREMENT'})
  return {
    state,
    dispatch,
    increment,
  }
}
```

To effectively use the Context API, read [this](https://kentcdodds.com/blog/state-colocation-will-make-your-react-app-faster).

Here are a few important things to remember when doing things this way:

1. Not everything in your application needs to be in a single state object. Keep things logically separated (user settings does not necessarily have to be in the same context as notifications). You will have multiple providers with this approach.
2. Not all of your context needs to be globally accessible! **Keep state as close to where it's needed as possible.**
