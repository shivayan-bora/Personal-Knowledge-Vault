---
id: oczq49as0hqvmuvnk8md6dy
title: GET
desc: ''
updated: 1654349356125
created: 1654348310904
---

To make a GET request, we use the `get()` method.

```js
axios.get('https://api.github.com/users/michaelficarra')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```
