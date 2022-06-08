---
id: 1ipohwlx1rg886x4j5hoqdk
title: Prop Drilling
desc: ''
updated: 1654589664449
created: 1654587084977
---

In this case, if we have multiple components in the same hierarchy, we can lift the state up to a common parent and drill it down to it's child components. This is called `prop-drilling`:

```jsx
 export default function Home() {
  const [country, setCountry] = useState('CA')
  return (
   <div>
    <CountryDetails country={country}/>
    <CountryPicker country={country} setCountry={setCountry}/>
   </div>
  )
 }

 function CountryPicker({country, setCountry}) {
  

  return (
   <select value={country} onChange={(event) => { 
    setCountry(event.target.value)}
   }>
    <option value='CA'>Canada</option>
    <option value='US'>United States of America</option>
   </select>
  )
 }

 function CountryDetails({country}) {
  return <h1>{country}</h1>
 }
```

However, if we have child components that's using the same piece of state that don't belong to the same hierarchy, we can lift the state upto the topmost common parent, however, it will have two problems:

1. When we drill the `prop` down to the children, any component that doesn't need the data will have access to the state.
2. When the state changes in any one of the parent, it will re-render the entire chain of components which might result in a performance hit.
3. It becomes unscalable and unmanageable once the complexity of the application increases.

To manage this, we use either [[Composition|cs.webdev.frontend.language.js.jsframework.react.state-management.types-of-application-state.client-state.design.composition]] or [[Global State|cs.webdev.frontend.language.js.jsframework.react.state-management.types-of-application-state.client-state.design.global-state]]
