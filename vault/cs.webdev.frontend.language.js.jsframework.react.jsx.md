---
id: yujc732og4lmlnynziayvm5
title: JSX
desc: ''
updated: 1653561490204
created: 1653560952532
---

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

To make sure our browsers understand the JSX syntax, we need to use a tool like [[Babel|cs.webdev.frontend.language.js.tools.babel]] to transpile our code into regular JavaScript that the browser can understand. In most modern React applications, you can add [[Babel|cs.webdev.frontend.language.js.tools.babel]] as an [[npm|cs.webdev.frontend.language.js.tools.npm]] dependency to transpile your entire project.

The [[Babel|cs.webdev.frontend.language.js.tools.babel]] transpiler will comvert the above JSX syntax into `React.createElement` functions as shown below:

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
