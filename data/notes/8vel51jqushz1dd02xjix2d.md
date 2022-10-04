
To make interactions with our elements, we use the `fireEvent` method from React Testing Library. #todo

```js
it('should be able to type into the input element', () => {
        render(
            <AddInput
                todos={[]}
                setTodos={mockedSetTodo}
            />
        )
        const inputElement = screen.getByPlaceholderText(/Add a new task here.../i)
        // Adding some value into an input text box
        // First parameter is the target element in which we want to fire an event on
        // Second is the value => Looks like event
        fireEvent.change(inputElement, { target: { value: 'Go Grocery Shopping' } })
        expect(inputElement.value).toBe('Go Grocery Shopping')
    })
```

```js
it('should have an empty input when add button is clicked', () => {
        render(
            <AddInput
                todos={[]}
                setTodos={mockedSetTodo}
            />
        )
        const inputElement = screen.getByPlaceholderText(/Add a new task here.../i)
        const buttonElement = screen.getByRole("button", { name: /Add/i })
        fireEvent.change(inputElement, { target: { value: 'Go Grocery Shopping' } })
        // Clicks the button
        fireEvent.click(buttonElement)
        expect(inputElement.value).toBe('')
    })
```
