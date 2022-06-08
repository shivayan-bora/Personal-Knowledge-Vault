---
id: a4giff4ll5fjz456rcnp7l1
title: usage
desc: ''
updated: 1654698786963
created: 1654698251036
---

1.For resources that don't need any extra parameters:

```jsx
useQuery(['labels'], fetchLabels); 
useQuery(['users'], fetchUsers); 
useQuery(['issues'], fetchIssues);
```

2.We can separate the different parts of our query key into separate items, like any parameters, IDs, indices - anything that our query depends on. These could be anything: literal strings, numbers, objects, or nested arrays.

```jsx
useQuery(['users', 1], fetchUser); 
useQuery(['labels', labelName], fetchLabel); 
useQuery(['issues', {completed: false}], fetchIssues);
```

To write an effective query key, we need to start with the most generic item to the most specific. However, to start off, it's best to put in a string key at the beginning of the array to uniquely identify the kind of data being fetched as well as identify it from the cache.

```jsx
useQuery(['issues', owner, repo], queryFn);
```

3.Make sure not to put the same query key for two different
