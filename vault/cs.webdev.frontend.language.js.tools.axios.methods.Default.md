---
id: 1p28s84b4yry4ecxq1u5le5
title: Default
desc: ''
updated: 1654348055806
created: 1654347819909
---

If we don't provide any method, by default, axios will call get.

```js
axios('/user')
```

If we send a config object, it will call the method specified in the config object. e.g. this will call the post method:

```js
axios({
  method: 'post',
  url: '/user',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
})
```
