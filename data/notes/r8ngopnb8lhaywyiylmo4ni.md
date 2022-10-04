
The first way to manage client state is through managing a local state.

```jsx
 export default function Home() {
  return (
   <div>
    <CountryPicker />
   </div>
  )
 }

 function CountryPicker() {
  const [country, setCountry] = useState('CA')

  return (
   <select value={country} onChange={(event) => { 
    setCountry(event.target.value)}
   }>
    <option value='CA'>Canada</option>
    <option value='US'>United States of America</option>
   </select>
  )
 }
```

This state is however limited to only one component i.e. the one that creates it. If we need to use the same data in multiple child components in the same hierarchy, we use [[`prop-drilling`|cs.webdev.frontend.language.js.jsframework.react.state-management.types-of-application-state.client-state.design.prop-drilling]]
