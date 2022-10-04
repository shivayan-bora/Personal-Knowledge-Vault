
The Redux API:

1. `applyMiddleare`
2. `compose`
3. `createStore`
4. `bindActionCreators`
5. `combineReducers`

There are some other API's we use in React-Redux but they aren't a part of Redux.

We have a `useReducer` hook in React but that doesn't have all the bells and whistles that Redux has e.g. middleware, dev tools, combining higher order functions etc. While we can use the `useReducer` hook for smaller applications but for larger applications we should use Redux.

Redux and Context API in React are somewhat similar. They both allow us to share state across components. The difference is that Redux is a state management library and Context API is a state sharing library. Redux is a state management library that allows us to manage state in a predictable way. Context API is a state sharing library that allows us to share state across components.

Also, internally Redux and `useReducer` uses the Context API in React-Redux. Context API in React-Redux gives access to the Store in your entire application.

`compose()` allows you to take a bunch of functions and create one function that will pass a value through each of them.

```js
const makeLouder = (string) => string.toUpperCase();
const repeatThreeTimes = (string) => string.repeat(3);
const embolden = (string) => string.bold();

const makeLouderrepeatThreeTimesembolden = (string) =>
  embolden(repeatThreeTimes(makeLouder(string)));
const makeLouderrepeatThreeTimesemboldenWithCompose = 
  compose(embolden, repeatThreeTimes, makeLouder);

console.log(makeLouderrepeatThreeTimesembolden("hello")); // <b>HELLOHELLOHELLO</b>
console.log(makeLouderrepeatThreeTimesemboldenWithCompose("hello")); // <b>HELLOHELLOHELLO</b> 
```

## Reducer

Pure Function. State of Application and something that happened comes in New State comes out.

![Reducer](2022-09-14-15-03-02.png)

`combineReducer`: A single reducer is not going to scale, hence we can divide it into smaller reducers and then combine them into a single reducer.

## Store

- `dispatch`:
- `subscribe`:
- `getState`: Get the current state of the application.
- `replaceReducer`: Takes an argument which is a new reducer and it swaps it out with the current one. Used for code splitting.

## Action

Action is an object where we mandatorily have an action type that tells the reducer on what kind of action it is.

You can have a payload as well.

```js
const incrementAction = {
  type: "INCREMENT",
  payload: 5,
};
```
