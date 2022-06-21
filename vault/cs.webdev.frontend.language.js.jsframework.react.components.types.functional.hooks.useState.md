---
id: 1k8uzahupveafng9uxud2kf
title: useState
desc: ''
updated: 1655708093277
created: 1655706069796
---

This is how we use the `useState` hook:

```jsx
const [state, setState] = useState(initialState);
```

This returns a stateful value and a function to update it.

During the initial render, the returned state is the same as the value passed as the first argument i.e. `initialState`.

The `setState` function is used to update the state. It accepts a new state value and enqueues a re-render of the component.

```jsx
setState(newState);
```

During subsequent re-renders, the first value returned by useState will always be the most recent state after applying updates.

**Note**: React guarantees that `setState` function identity is stable and won’t change on re-renders. This is why it’s safe to omit from the `useEffect` or `useCallback` dependency list.
