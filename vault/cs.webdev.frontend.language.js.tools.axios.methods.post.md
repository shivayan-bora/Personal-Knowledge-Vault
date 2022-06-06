---
id: 0dyb1w8loomr1bk2dvqnmpm
title: POST
desc: ''
updated: 1654434618976
created: 1654432934987
---

To make a POST request in axios, we use the post method.

```js
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```
