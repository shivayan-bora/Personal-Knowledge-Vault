---
id: jiiyjbgd40wa0v2pv0ehg3e
title: createElement
desc: ''
updated: 1654350274627
created: 1653560638391
---

In order to create a UI with React's `createElement` API:

```html
<body>
    <div id="root"></div>
    <script type="text/javascript">
        const rootElement = document.getElementById('root')
        const element = React.createElement('div', {
            className: 'container',
            children: 'Hello World'
        })
    ReactDOM.render(element, rootElement) // As per React 18, this is not the way to attach the app to the root element
    </script>
</body>
```

- The `createElement` creates a React Element which is an object.
- Some ways to specify the children:

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

But we don't need to use the create our DOM nodes like this. We use [[Compiling JSX|cs.webdev.frontend.language.js.jsframework.react.jsx.compiling-jsx]] to do the same.
