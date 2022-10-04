
A query is a declarative dependency to some asynchronous source of data that's tied to a unique key. Basically, it's what React Query uses to fetch data from a server with any Promise based method (inclusing GET or POST Methods).

What makes React Query really powerful, is it's ability to create and maintain a cache for each one of it's queries. To accomplish this, React Query uses two things:

1. QueryClient
2. QueryClientProvider

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

Next up, we need to use the [[useQuery|cs.webdev.frontend.language.js.jsframework.react.state-management.tools.react-query.apis.useQuery]] hook to create new queries.
