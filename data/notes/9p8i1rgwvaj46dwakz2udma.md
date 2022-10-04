
Similar to [[cs.webdev.frontend.language.js.testing.tools.jest.assertion]] in Jest.

Some examples:

```js
const MockTodoFooter = ({ numberOfIncompleteTasks }) => {
    return (
        <BrowserRouter>
            <TodoFooter numberOfIncompleteTasks={numberOfIncompleteTasks} />
        </BrowserRouter>
    )
}

it('should render the correct amount of incomplete tasks', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={5} />)
    const paragraphElement = screen.getByText(/5 tasks left/i)
    expect(paragraphElement).toBeInTheDocument()
})

it('should render "task" when the number of incomplete tasks is one - 1', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    expect(paragraphElement).toBeInTheDocument()
})

it('should render "task" when the number of incomplete tasks is one - 2', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    // The element is actually visible to the end user. So making the opacity to 0 of an element will render the component not visible to the end user. This is just one of the ways to make a component invisible.
    expect(paragraphElement).toBeVisible()
})

it('should render "task" when the number of incomplete tasks is one - 3', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    expect(paragraphElement).toBeTruthy();
})

it('should render "task" when the number of incomplete tasks is one - 4', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    expect(paragraphElement).toContainHTML('p');
})

it('should render "task" when the number of incomplete tasks is one - 5', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    expect(paragraphElement).toHaveTextContent('1 task left');
})

it('should render "task" when the number of incomplete tasks is one - 6', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    // `not` negates the assertion
    expect(paragraphElement).not.toBeFalsy();
})

it('should render "task" when the number of incomplete tasks is one - 7', () => {
    render(<MockTodoFooter numberOfIncompleteTasks={1} />)
    const paragraphElement = screen.getByText(/1 task left/i)
    // We get an element which has some attributes that we can access
    expect(paragraphElement.textContent).toHaveTextContent('1 task left');
})
```
