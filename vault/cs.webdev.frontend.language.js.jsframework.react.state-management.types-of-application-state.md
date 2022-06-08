---
id: 6lyjwtn45ii5e4cpkmqfkrp
title: Types of Application State
desc: ''
updated: 1654612029072
created: 1654539888632
---

In React, we need to consider state into two parts: Client state and Server State. These two aren't the same thing.

- **Server Cache**: State that's actually stored on the server, that we store in the client for quick-access. (e.g. User Data).
- **UI State**: State that's only useful for the UI to  control interactivity of different parts of the app. (e.g. modal `isOpen` state).

You can use React for UI state. As a matter of fact, React is designed to handle this UI state for us.

You can use React Query for your server cache.

Some key points:

- Server cache !== UI State. Use React Query for Server Cache. (Checkout Remix)
- React is a state management library.
- Lift state up (or down! [**Colocation**](https://kentcdodds.com/blog/state-colocation-will-make-your-react-app-faster)).
- Use composition when `prop-drilling` is a pain (and sometimes use Context).
- If performance is an issue, use `jotai`.

References:

1. [Application State Management with React](https://kentcdodds.com/blog/application-state-management-with-react).
2. [React State Management from Lee Robinson](https://leerob.io/blog/react-state-management#state-management-options)
