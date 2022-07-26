---
id: 7jgurh48dzmf8h9zbjz994n
title: Async
desc: ''
updated: 1658736274403
created: 1658736255554
---

To test async functions:

```js
const fetchData = require('./async')

it('should return correct data', () => {
    fetchData(1).then(data => {
        expect(data.id).toEqual(1)
    })
})

it('should return correct data', async () => {
    const data = await fetchData(1)
    expect(data.id).toEqual(1)
})
```
