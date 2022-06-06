---
id: byrhx132lt2zk3qgzltw8x6
title: Multiple Requests
desc: ''
updated: 1654434712593
created: 1654434679122
---

For performing multiple concurrent requests:

```js
function getUserAccount() {
  return axios.get('/user/12345');
}

function getUserPermissions() {
  return axios.get('/user/12345/permissions');
}

Promise.all([getUserAccount(), getUserPermissions()])
  .then(function (results) {
    const acct = results[0];
    const perm = results[1];
  });
```
