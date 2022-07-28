---
id: vyrivvmu5hdizdvy7aokqkt
title: Describe
desc: ''
updated: 1658935749320
created: 1658934758210
---

Similar to [[cs.webdev.frontend.language.js.testing.tools.jest.test-suite]] from Jest.

Used to group multiple related test blocks into a single group.

We can nest multiple `describe` blocks into one another.

```js
describe('Header', () => {
    it('should render same text passed into title prop when searched by text', () => {
        render(<Header title='My Header' />)
        const headingElement = screen.getByText(/my header/i)
        expect(headingElement).toBeInTheDocument()
    })
})
```

or

```js
const MockTodoFooter = ({ numberOfIncompleteTasks }) => {
    return (
        <BrowserRouter>
            <TodoFooter numberOfIncompleteTasks={numberOfIncompleteTasks} />
        </BrowserRouter>
    )
}

describe("TodoFooter", () => {
    it('should render the correct amount of incomplete tasks', () => {
        render(<MockTodoFooter numberOfIncompleteTasks={5} />)
        const paragraphElement = screen.getByText(/5 tasks left/i)
        expect(paragraphElement).toBeInTheDocument()
    })

    it('should render "task" when the number of incomplete tasks is one', () => {
        render(<MockTodoFooter numberOfIncompleteTasks={1} />)
        const paragraphElement = screen.getByText(/1 task left/i)
        expect(paragraphElement).toBeInTheDocument()
    })
})
```
