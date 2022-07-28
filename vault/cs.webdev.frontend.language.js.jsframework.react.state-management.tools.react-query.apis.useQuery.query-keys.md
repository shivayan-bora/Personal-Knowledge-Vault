---
id: x9oyvrcqbt8qs8rjbd8ra0t
title: Query Keys
desc: ''
updated: 1654754342664
created: 1654697739864
---

A query key is something that's used to uniquely identify the queries. This same query key is used to uniquely identify the query data from the cache. This makes it possible to use the same query data multiple times without making any further duplicate requests.

Query keys behave the exact same as the useEffect dependency array. Each item in the query key will cause the query to refetch when it changes. e.g. the following query will refetch when the `username` variable changes.

```jsx
useQuery(['user', username], fetchUser);
```

That means the query key has a direct connection to the query function. Any values in the query function that could change should be put somewhere in our query key, so React Query knows to rerun the query function when they do change. Most query keys will use strings and numbers as their array items, but Objects are also useful.

**Note:** The order of our query key array is important, since reordering the items would change the query key.

**Note:** React Query v4 only supports arrays as query keys.
