
Server state consists of data that's persisted in the backend servers and sent to the UI through API Calls. e.g. user data, post data, comment data etc.

This is the data that needs to be persisted across browser sessions.

There's one more thing that we need to consider when it comes to server state. Multiple clients can access the server's data and manipulate it at any time. This has huge implications on how we store Server state over at the client.

React is notoriously unopinionated when it comes to managing Server State. The only recommendation that React provides is to fetch the data inside a useEffect hook which deals with any kind of side effects in the application which includes async operations.
