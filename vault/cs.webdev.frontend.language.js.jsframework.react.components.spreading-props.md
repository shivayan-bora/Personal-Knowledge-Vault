---
id: 6v026gbdppe969wfl6sdung
title: Spreading Props
desc: ''
updated: 1655645931826
created: 1655633311279
---

While spreading `props` make sure to check how to put your properties, because in the event of conflict, the property that comes later is the one that overrides the others.

```jsx
const Box = ({style, size='', ...otherProps}) => {
  const boxSizeClassName = size ? `box--${size}` : ''
  return <div className={`box ${boxSizeClassName}`} style={{fontStyle: 'italic', ...style}} {...otherProps}/>
}
```

You can access the rest of the `props` by using the `otherProps` property.
