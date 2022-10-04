
The useQueries hook can be used to fetch data from multiple queries. It accepts an array with query options similar to useQuery hook and it returns an array with all the query results.

```jsx
 const results = useQueries([
   { queryKey: ['post', 1], queryFn: fetchPost },
   { queryKey: ['post', 2], queryFn: fetchPost },
 ])
```
