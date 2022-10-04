
When it comes to managing state, people usually prefer a global state management systems like Redux or MobX. These libraries can work, however,they introduce more problems treating the server state the same as the client state and using a global store.

What we need is a library that takes care specifically of the server state, something that handles errors, loads the server state and handles all the server state [[Requirements|cs.webdev.frontend.language.js.jsframework.react.state-management.types-of-application-state.server-state.requirements]].

 React Query solves all of them - most of them automatically! And even though React Query ships with sensible defaults, pretty much every aspect of how it fetches, stores, and delivers your server state can be configured.
