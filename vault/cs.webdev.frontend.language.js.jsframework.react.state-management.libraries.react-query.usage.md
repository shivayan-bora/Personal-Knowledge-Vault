---
id: qry9gtne0mca1rjtj7x40uh
title: useQuery
desc: ''
updated: 1654696034699
created: 1654695515682
---

What makes React query really powerful, is it's ability to create and maintain a cache for each one of it's queries. To accomplish this, React Query uses two things:

1. [[QueryClient|cs.webdev.frontend.language.js.jsframework.react.state-management.react-query.QueryClient]]
2. [[QueryClientProvider|cs.webdev.frontend.language.js.jsframework.react.state-management.react-query.QueryClientProvider]]

Firstly, we need to create a QueryClient and wrap our entire application with a QueryClientProvider which makes the QueryClient cache available to the entire application.

```jsx
import ReactDOM from 'react-dom'
import App from './App' 
import { QueryClient, QueryClientProvider } from 'react-query'

const queryClient = new QueryClient(); 

ReactDOM.render( 
    <QueryClientProvider client={queryClient}> 
        <App /> 
    </QueryClientProvider>
    , document.getElementById('root')
);
```

Next up, we need to use the [[useQuery|cs.webdev.frontend.language.js.jsframework.react.state-management.react-query.useQuery]] hook to create new queries.
