---
id: 3k3jut4tw2brwahs3j28qqz
title: Composition
desc: ''
updated: 1654590060065
created: 1654589665709
---

Instead of making components that render other components and wiring props everywhere like this:

```jsx
 function App() {
  const [someState, setSomeState] = React.useState('some state')
  return <>
   <Header someState={someState} onStateChange={setSomeState} />
   <LeftNav someState={someState} onStateChange={setSomeState} />
   {/* ... */}
  </>
 }
```

Maybe you can compose things together (Vue isn't the only one with `slots`. React had them from Day 1):

```jsx
 function App() {
  const [someState, setSomeState] = React.useState('some state')
  return <>
   <Header 
    logo={<Logo someState={someState} />}
    settings={<Settings onStateChange={setSomeState} />} 
   />
   <LeftNav>
    <SomeLink someState={someState} />
    <SomeOtherLink someState={someState} />
    <Etc someState={someState} />
   </LeftNav>
   {/* ... */}
  </>
 }
```
