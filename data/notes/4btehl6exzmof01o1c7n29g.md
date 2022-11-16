
In contrast to `fetch` and `XMLHttpRequest`, Axios treats all errors as errors and not just network errors.

Since Axios is a promise based HTTP client, it has a `catch` method which is called when the promise is rejected.

```js
axios.get('https://api.github.com/users/michaelficarra')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```
