---
id: iyolqttxxao1zjmdhwnov8l
title: Custom Hook
desc: ''
updated: 1654759057927
created: 1654758938953
---

We can also use a custom hook to provide the same query in multiple components. This lets us keep the query function local to the query that is using it while still allowing the query to be used across multiple components.

```js
function useGithubIssuesQuery({ owner, repo, filters }) {
  function getIssues() {
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
    ).then(res => res.json());
  }

  return useQuery(
    ["issues", owner, repo, filters],
    getIssues
  );
}
```

We can now use this in any component anywhere in our app and be confident that all of the queries are sharing the same cache data and minimizing the number of network requests.
