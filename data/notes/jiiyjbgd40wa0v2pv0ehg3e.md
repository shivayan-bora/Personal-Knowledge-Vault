
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

The `createElement` creates a React Element which is an object.

But we don't need to use the create our DOM nodes like this. We use [[Compiling JSX|cs.webdev.frontend.language.js.jsframework.react.jsx.compiling-jsx]] to do the same.
