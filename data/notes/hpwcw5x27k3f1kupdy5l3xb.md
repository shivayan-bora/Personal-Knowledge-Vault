
When we make any request to the server, it basically takes sometime for us to receive the data as the data has to travel through vast distances of copper and fiber optic cables, not to mention the time it takes for the server to process as well. Even at the speed of light, it takes a request about 100 milliseconds to round trip from New York to Australia.

**Might need a new note**:

The Fetch API The fetch API is the easiest way to make network requests in the browser. It uses a Promise API to handle the async request. Show More Notice how it uses a chained .then() to get the actual data. The first response parameter is the raw HTTP response, that includes the status code and headers.

```js
    fetch(url).then((response) => response.json())
```

Once you have the response, there are a few options to get the response body – `response.json()` parses the body as JSON, `response.text()` parses it as text, and `response.arrayBuffer()` returns the raw bytes that came back.
