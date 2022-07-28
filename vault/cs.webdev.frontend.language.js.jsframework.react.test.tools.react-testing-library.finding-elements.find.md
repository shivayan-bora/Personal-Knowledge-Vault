---
id: juasj6stzaklgy589ka513r
title: Find
desc: ''
updated: 1658928892398
created: 1658928881063
---

```js
it('should render same text passed into title prop when searched by text', async () => {
        render(<Header title='My Header' />)
        const headingElement = await screen.findByText(/my header/i)
        expect(headingElement).toBeInTheDocument()
})
```
