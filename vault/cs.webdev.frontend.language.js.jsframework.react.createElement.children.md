---
id: u9dnc27kcaf790r0t9cixsr
title: Children
desc: ''
updated: 1654611492392
created: 1654586494914
---

Some ways to specify the children:

```jsx
React.createElement('div', {
    className: 'container',
    children: 'Hello World'
})
```

```jsx
React.createElement('div', {
    className: 'container',
    children: ['Hello World', 'Goodbye World']
})
```

```jsx
React.createElement('div', {
    className: 'container',
}, 'Hello World', 'Goodbye World')
```

- Putting React elements as `children`:

```jsx
React.createElement('div', {
    className: 'container',
    children: React.createElement('span', null, 'Hello', 'World')
})
```

This will look like:

```html
<div class='container'>
    <span>HelloWorld</span>
</div>
```
