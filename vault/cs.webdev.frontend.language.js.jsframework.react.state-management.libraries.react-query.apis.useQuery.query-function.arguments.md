---
id: cga1j71wd3t37zm7svs84rg
title: Arguments
desc: ''
updated: 1654758950586
created: 1654758754251
---

We can pass arguments into a Query Function in two ways:
1.By using an Arrow function:

```js
const userQuery = useQuery(
  ["user", username],
 () => getGithubUser(username),
);
```

2.Using the query keys which is more helpful and resilient:

```jsx
await function getGithubUser({ queryKey }) {
  const [user, username] = queryKey;

  return fetch(`https://api.github.com/users/${username}`)
    .then((res) => res.json());
};

const User = ({ username }) => {
  const userQuery = useQuery(
    ["user", username],
    getGithubUser,
  );

  if (userQuery.isLoading) {
    return <p>Getting user...</p>;
  }

  if (userQuery.error) {
    return (
      <p>Error getting user: {userQuery.error.message}</p>
    );
  }

  return <p>{userQuery.data.name}</p>;
};
```

Or even a more complex scenario like:

```jsx
function getIssues({ queryKey }) {
  const [issues, owner, repo, filters] = queryKey;

  const filterQuery = new URLSearchParams();

  if (filters.assignee) {
    filterQuery.append("assignee", filters.assignee);
  }  

  if (filters.labels && filters.labels.length > 0) {
    filterQuery.append("labels", filters.labels.join(","));
  }  

  if (filters.state) {
    filterQuery.append("state", filters.state);
  }  

  const filterQueryString = filterQuery.toString();

  return fetch(
    `https://api.github.com/repos/${owner}/${repo}/issues${
      filterQueryString ? `?${filterQueryString}` : ""
    }`,
  ).then((res) => res.json());
}

function Issues({ owner, repo }) {
  const [issueState, setIssueState] = useState("open");
  const [assignee, setAssignee] = useState();
  const [labels, setLabels] = useState("");

  const issuesQuery = useQuery(
    [
      "issues",
      owner,
      repo,
      { 
        state: issueState, 
        assignee, 
        labels: labels || undefined 
      },
    ],
    getIssues,
  );
  
  ...
}
```
