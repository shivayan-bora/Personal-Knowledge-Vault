---
id: ewf0v9091uh6yb3pp8khc57
title: Spy
desc: ''
updated: 1658750915263
created: 1658750501078
---

Consider the following:

```js
const axios = require('axios')

const fetchData = async (id) => {
    const results = await axios.get(`https://jsonplaceholder.typicode.com/todos/${id}`)
    return results.data
}
```

Here we don't want to actually make an HTTP `axios.get` request. So we can `spyOn` the axios module. You can consider spying on something as a mock i.e. instead of the spied function having an implementation, we're going to spy on it and return the mock value that we want.

```js
it('mock axios', async () => {
    // 1st parameter is the module we want to spy on
    // 2nd parameter is what method do we want to spy on in the module
    jest.spyOn(axios, 'get').mockReturnValueOnce({
        data: {
            id: 1,
            todo: 'Get 1M subscribers'
        }
    });
    const results = await fetchData(1);

    expect(results.todo).toBe('Get 1M subscribers');
})
```
