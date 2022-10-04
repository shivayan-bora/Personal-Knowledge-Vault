
Testing different units/components together.

```js
const MockTodo = () => {
    return (
        <BrowserRouter>
            <Todo />
        </BrowserRouter>
    )
}

const addTask = (tasks) => {
    const inputElement = screen.getByPlaceholderText(/Add a new task here.../i)
    const buttonElement = screen.getByRole('button', { name: /add/i })
    tasks.forEach(task => {
        fireEvent.change(inputElement, { target: { value: task } })
        fireEvent.click(buttonElement)
    });
}

describe('Header', () => {
    it('should render same text passed into title prop', () => {
        render(<MockTodo />)
        addTask(['Go Grocery Shopping'])
        const divElement = screen.getByText(/Go grocery shopping/i)
        expect(divElement).toBeInTheDocument()
    })

    it('should render multiple items', () => {
        render(<MockTodo />)
        addTask(['Go Grocery Shopping', 'Pet My cat', 'Go To The Gym'])
        const divElements = screen.getAllByTestId('task-container')
        expect(divElements.length).toBe(3)
    })

    it('task should not have completed class when initially rendered', () => {
        render(<MockTodo />)
        addTask(['Go Grocery Shopping'])
        const divElement = screen.getByTestId('task-container')
        expect(divElement).not.toHaveClass("todo-item-active")
    })

    it('task should have completed class when clicked', () => {
        render(<MockTodo />)
        addTask(['Go Grocery Shopping'])
        const divElement = screen.getByTestId('task-container')
        fireEvent.click(divElement)
        expect(divElement).toHaveClass("todo-item-active")
    })
})
```
