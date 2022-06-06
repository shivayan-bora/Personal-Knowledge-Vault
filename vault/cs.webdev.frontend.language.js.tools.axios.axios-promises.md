---
id: wxslcdg78drjp87h8lcwu91
title: Axios Promises
desc: ''
updated: 1654540785303
created: 1654349676407
---

Once an HTTP request is made, it returns a promise that's either fulfilled or rejected as per the response sent by the server.
If the promise is fulfilled, the first argument of `then()` will be called; if the promise is rejected, the second argument will be called.
According to the documentation, the fulfillment value is an object containing the following information:

```json
    { 
        // `data` is the response that was provided by the server 
        data: {}, 
        // `status` is the HTTP status code from the server response 
        status: 200, 
        // `statusText` is the HTTP status message from the server response 
        statusText: 'OK', 
        // `headers` the headers that the server responded with 
        // All header names are lower cased 
        headers: {}, 
        // `config` is the config that was provided to `axios` for the request 
        config: {}, 
        // `request` is the request that generated this response 
        // It is the last ClientRequest instance in node.js (in redirects) 
        // and an XMLHttpRequest instance the browser 
        request: {} 
    }
```
