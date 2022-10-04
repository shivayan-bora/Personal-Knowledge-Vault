
State is any piece of data that changes over time. When we consider any piece of data that changes overtime, that complicates a lot of things. If we had a static piece of data, we can stick to a server template and deploy it over a CDN which will then serve the data to wherever it is needed.

In case of React, the React UI is a function of it's state. Whenever we consider React components, we usually think of it as Lego blocks that we can fit anywhere to build our systems. However the same mentality is not kept when we think about state management.

The key to a good solution to the state management solution is to think of the application state as how it maps to the application tree.

- It's a difficult problem to solve.
- It's usually over engineered.

**Note**: We must remember that React in itself a state management library with the presence of `useState` or `useContext` hook.
