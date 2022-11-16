
This is how you use a `useRef` hook:

```jsx
function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const onButtonClick = () => {
    // `current` points to the mounted text input element
    inputEl.current.focus();
  };
  return (
    <>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </>
  );
}
```

`useRef` returns a mutable `ref` object whose `.current` property is initialized to the passed argument (`initialValue`). The returned object will persist for the full lifetime of the component. It gets pesisted across multiple renders of the component.
