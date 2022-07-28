---
id: zwv8tszsjunz4bevigdgfu0
title: Query
desc: ''
updated: 1658929136237
created: 1658928900786
---

It will not error out if the match isn't found.

```js
    it('should render same text passed into title prop when searched by text', () => {
        render(<Header title='My Header' />)
        const headingElement = screen.queryByText(/dog/i)
        expect(headingElement).not.toBeInTheDocument()
    })
```
