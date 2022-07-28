---
id: 3m33su0agj9nqvkvlixifit
title: Mock
desc: ''
updated: 1658936273484
created: 1658936211548
---

React Testing Library also uses [[cs.webdev.frontend.language.js.testing.tools.jest.mock]] functions from jest.

```js
const mockedSetTodo = jest.fn()

describe('AddInput', () => {
    it('should render input element', () => {
        render(
            <AddInput
                todos={[]}
                // We don't care about the setTodos function as we are just trying to render the component
                setTodos={mockedSetTodo}
            />
        )
        const inputElement = screen.getByPlaceholderText(/Add a new task here.../i)
        expect(inputElement).toBeInTheDocument()
    })
})
```
