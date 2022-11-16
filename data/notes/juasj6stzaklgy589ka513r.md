
```js
it('should render same text passed into title prop when searched by text', async () => {
        render(<Header title='My Header' />)
        const headingElement = await screen.findByText(/my header/i)
        expect(headingElement).toBeInTheDocument()
})
```
