
Forms can be handled in React in the following manner:

```jsx
function UsernameForm({onSubmitUsername}) {
  const [username, setUsername] = React.useState('')
  const inputField = useRef(null)

  const handleSubmit = event => {
    event.preventDefault()
    onSubmitUsername(username)
  }

  const handleChange = () => {
    const value = inputField.current.value
    setUsername(value.toLowerCase())
  }

  return (
      <form onSubmit={handleSubmit}>
        <div>
          <label htmlFor='username'>Username:</label>
          <input name="username" type="text" ref={inputField} onChange={handleChange} value={username}/>
        </div>
        <button type="submit">Submit</button>
      </form>
  )
}
```

There are a few key things to notice:

1. The `form` element has an `onSubmit` event handler that will handle the form submission.
2. The default behavior of forms is to submit a POST request to the local server with the form values as query parameters. In order to prevent the default behaviour, we need to use `event.preventDefault()`.
3. In HTML, in `label` element, we use the `for` keyword to tie it to a form field. However, in JS, `for` is a reserved keyword and hence, we use `htmlFor` for the same purpose.
4. In this case, we are managing the input field with a local state using the [[cs.webdev.frontend.language.js.jsframework.react.components.types.functional.hooks.useState]] hook to make it into a controlled input field. for that we need to provide a `value` tied to the state and an `onChange` handler to update the state.
5. In case we didn't provide an `onChange` handler, it will be a read only field and you won't be able to enter any value in it.
6. We can also pass a default value to the input field through a `defaultValue` property.
7. We can also capture the input field value if we tie it to a `ref` using the [[cs.webdev.frontend.language.js.jsframework.react.components.types.functional.hooks.useRef]] Hook.
