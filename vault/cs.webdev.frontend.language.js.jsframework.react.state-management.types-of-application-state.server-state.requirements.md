---
id: fo7ae2wgrgcipwtbhfqag8b
title: Requirements
desc: ''
updated: 1654688681710
created: 1654688678550
---

When it comes to requirements for fetching server data, we need to keep the following things in mind:

1. Rendering the same data across multiple components without doing re-fetches.
2. De-duplicating identical requests.
3. Using a cache to limit the number of `fetch` requests.
4. Automatically refetching to have the freshest data.
5. Handling pagination.
6. Updating our local data when we make mutations to the remote data.
7. Orchestrating requests that depend on the result of other requests
