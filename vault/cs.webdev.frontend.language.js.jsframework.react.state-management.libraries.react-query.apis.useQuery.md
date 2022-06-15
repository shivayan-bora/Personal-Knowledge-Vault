---
id: ww7p3t6ym4hxbwe18wa4s8r
title: useQuery
desc: ''
updated: 1655306220533
created: 1654695992268
---

This hook performs the data fetching, caches the results, and provides us with the state of the query. The object returned by useQuery includes the fetched data (`query.data`), the state of the query (`isLoading`, `isSuccess` and `isError`), and a bunch of methods for interacting with the query.

Any time the query function throws an error or returns a rejected promise, React Query will treat that as an error, setting the `isError` state to `true`, and setting the `error` property to the thrown or rejected value.

### Usage

```jsx

import { useQuery } from 'react-query'

function fetchUser (username) { 
    return fetch(`https://api.github.com/users/${username}`).then((res) => res.json()) 
}

export default function GithubUser({ username }) { 
    const userQuery = useQuery( [username], () => fetchUser(username) ); 
    const data = userQuery.data ... 
}
```

`useQuery` accepts two arguments, a query key and a query function.

1. The query key is an array used to keep track of the query in the cache. Whenever any of the items in the query key change, React Query treats it as a new query and will fetch new data.
2. The query function is the function that actually fetches the data.
