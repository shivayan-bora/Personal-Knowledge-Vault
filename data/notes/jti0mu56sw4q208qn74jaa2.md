
To pass in the headers with Axios:

- GET Request: The second argument is the headers.

```js
axios.get(url, {})
```

- POST Request: The third argument alongwith the data is the header.

```js
axios.post(url,{data},{})
```

One small example would be:

```js
const { data } = await axios.get(url, {
        headers: { Accept: 'application/json' },
      });
```
