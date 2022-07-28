---
id: whlqanpcrioshun6xef07cq
title: Mutations
desc: ''
updated: 1655307004218
created: 1655305683415
---

Unlike queries, mutations are used to perform CRUD operations on data or perform server side-effects. For this, we can use a [[useMutation|cs.webdev.frontend.language.js.jsframework.react.state-management.tools.react-query.apis.useMutation]] hook.

```jsx
function App() {
   const mutation = useMutation(newTodo => {
     return axios.post('/todos', newTodo)
   })

   return (
     <div>
       {mutation.isLoading ? (
         'Adding todo...'
       ) : (
         <>
           {mutation.isError ? (
             <div>An error occurred: {mutation.error.message}</div>
           ) : null}

           {mutation.isSuccess ? <div>Todo added!</div> : null}
 
           <button
             onClick={() => {
               mutation.mutate({ id: new Date(), title: 'Do Laundry' })
             }}
           >
             Create Todo
           </button>
         </>
       )}
     </div>
   )
 }
```
