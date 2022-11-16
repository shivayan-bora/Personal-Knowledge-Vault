
It will error out causing the tests to fail if the match isn't found.

`getByText`: Find by text

```js
it('should render same text passed into title prop when searched by text', () => {
    render(<Header title='My Header' />)
    const headingElement = screen.getByText(/my header/i)
    expect(headingElement).toBeInTheDocument()
})
```

`getByRole`: Find by role e.g. button, header, paragraph etc. Press `ctrl+space` to find all the permissible values.

```js
it('should render same text passed into title prop when searched by role', () => {
    render(<Header title='My Header' />)
    const headingElement = screen.getByRole("heading")
    expect(headingElement).toBeInTheDocument()
})
```

If this returns multiple headers, it will fail the test. To make sure that doesn't happen, we can do a search on the contents of the element as follows:

```js
it('should render same text passed into title prop when searched by role', () => {
    render(<Header title='My Header' />)
    const headingElement = screen.getByRole("heading", { name: "My Header" })
    expect(headingElement).toBeInTheDocument()
})
```

You can use a semantic queries also:

```html
    <>
        <h1 className="header" title="Header">{title}</h1>
    </>
```

```js
it('should render same text passed into title prop when searched by role', () => {
    render(<Header title='My Header' />)
    const headingElement = screen.getByTitle("Header")
    expect(headingElement).toBeInTheDocument()
})
```

`getAllByRole`:

```js
    it('should render all headers when searched by role', () => {
        render(<Header title='My Header' />)
        const headingElement = screen.getAllByRole("heading")
        expect(headingElement.length).toBe(2)
    })
```
