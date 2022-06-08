---
id: x9oyvrcqbt8qs8rjbd8ra0t
title: query-keys
desc: ''
updated: 1654698082716
created: 1654697739864
---

A query key is something that's used to uniquely identify the query keys. This same query key is used to uniquely identify the query data from the cache. This makes it possible to use the same query data multiple times without making any further duplicate requests.

Query keys behave the exact same as the useEffect dependency array. Each item in the query key will cause the query to refetch when it changes. e.g. the following query will refetch when the `username` variable changes.

```jsx
useQuery(['user', username], fetchUser);
```

**Note:** React Query v4 only supports arrays as query keys.
