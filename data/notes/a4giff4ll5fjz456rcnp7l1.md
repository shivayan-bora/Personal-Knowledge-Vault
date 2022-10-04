
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

3.To write an effective query key, we need to start with the most generic item to the most specific. However, to start off, it's best to put in a string key at the beginning of the array to uniquely identify the kind of data being fetched as well as identify it from the cache.

```jsx
useQuery(['issues', owner, repo], queryFn);
```

4.Make sure not to put the same query key for two different different queries as they will overlap each other's data based on whatever was called later. e.g.:

```jsx
const usersQuery = useQuery([userId], fetchUsers); 
const commentsQuery = useQuery([commentId], fetchComments);
```

If we use incrementing id's for both users and comments, at one point when both of them have a value of `1`, it will cause a key collision and it will override the data in the cache.

5.We can also use Objects in the query key. e.g. Let's imagine the following scenario:

Here's what that Github URL looks like when using a filter to get only closed issues: [https://api.github.com/repos/uidotdev/usehooks/issues?state=closed].
Here, we're keeping the `open` and `closed` state in React state. The most naïve approach would be to to put the filter in as the last item of the query key array.

```jsx
function Issues({ owner, repo }) { 
    const [issueState, setIssueState] = useState('open'); 
    const issuesQuery = useQuery( ['issues', owner, repo, issueState], queryFn ); 
    ... 
} 
```

This would work just fine. Whenever our state changes, the query will rerun. If we have multiple sets of filters, since changing the order of the array will change the query key, we can have filter as an object, so now the order doesn't matter.

```jsx
function Issues({ owner, repo }) { 
    const [issueState, setIssueState] = useState('open'); 
    const [assignee, setAssignee] = useState(); 
    const [labels, setLabels] = useState(''); 
    const issuesQuery = useQuery( [ 'issues', 
                                    owner, 
                                    repo, 
                                    { 
                                        state: issueState, 
                                        assignee, 
                                        labels: labels || undefined 
                                    }, 
                                ]
                                , queryFn ); 
    ... 
}
```
