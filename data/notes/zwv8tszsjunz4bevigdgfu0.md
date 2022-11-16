
It will not error out if the match isn't found.

```js
    it('should render same text passed into title prop when searched by text', () => {
        render(<Header title='My Header' />)
        const headingElement = screen.queryByText(/dog/i)
        expect(headingElement).not.toBeInTheDocument()
    })
```
