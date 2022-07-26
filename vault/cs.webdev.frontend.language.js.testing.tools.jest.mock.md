---
id: w0ywzhyy6l2f9gds30a0bi4
title: Mock
desc: ''
updated: 1658743468245
created: 1658738647964
---

Imagine the following function:

```js
const fetchData = async (id) => {
    const results = await axios.get(`https://jsonplaceholder.typicode.com/todos/${id}`)
    ... // validation and other processes
    return results.data
}
```

Let's assume the function consists of a lot of validation and other process. In this case, we're banking on the fact that the API call will get resolved successfuly. The API call can fail due to various reasons, e.g. server failure etc.

However, even if the API call fails, we need to test if our function is correctly written.

So here, instead of making an actual API call, we will mock the API call and stub a function (or mock) that will always be successful and return us a data object. In this case, we can test our function implementation regardless of the API call.
