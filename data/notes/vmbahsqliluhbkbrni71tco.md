
In order to create a UI with JSX:

```html
<body>
    <div id="root"></div>
    <script type="text/javascript">
        const rootElement = document.getElementById('root')
        const element = <div className="container">Hello World</div>
        ReactDOM.render(element, rootElement) // As per React 18, this is not the way to attach the app to the root element
    </script>
</body>
```

Unfortunately, this syntax i.e. `<div></div>` is not understood by the browser natively inside a script tag. This syntax is called JSX.
