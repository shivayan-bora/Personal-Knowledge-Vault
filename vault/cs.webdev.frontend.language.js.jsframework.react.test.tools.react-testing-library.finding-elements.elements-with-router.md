---
id: c94usudbgkp1rmdytku1jox
title: Elements with Router
desc: ''
updated: 1658934105795
created: 1658933825654
---

Imagine the following component:

```jsx
function TodoFooter({
    numberOfIncompleteTasks
}) {
    return (
        <div className="todo-footer">
            <p>{numberOfIncompleteTasks} {numberOfIncompleteTasks === 1 ? "task" : "tasks"} left</p>
            <Link to="/followers">Followers</Link>
        </div>
    )
}
```

If we write the tests like this:

```js
it('should render the correct amount of incomplete tasks', () => {
    render(<TodoFooter numberOfIncompleteTasks={5} />)
    const paragraphElement = screen.getByText(/5 tasks left/i)
    expect(paragraphElement).toBeInTheDocument()
})
```

This test will fail as we have a `Link` element inside the `TodoFooter` component and all the `Link` components should lie within a `<BrowserRouter>`. As we are rendering the component in a standalone way, this doesn't happen. To fix this, we need to wrap our `TodoFooter` in a `BrowserRouter` component as follows:

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
```
