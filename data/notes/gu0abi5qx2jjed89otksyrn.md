
We can pass specific classes to an HTML element using the `class` attribute, similarly, for React components we use the `className` prop.

We use `className` as the `prop` name because `class` is a reserved keyword in JavaScript.

```jsx
const largeBox = <div style={{backgroundColor: 'orange', fontStyle: 'italic'}} className="box box--large">large orange box</div>
```
