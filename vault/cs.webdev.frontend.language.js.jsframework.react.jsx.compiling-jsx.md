---
id: yujc732og4lmlnynziayvm5
title: Compiling JSX
desc: ''
updated: 1654350412624
created: 1653560952532
---

To make sure our browsers understand the JSX syntax, we need to use a tool like [[Babel|cs.webdev.frontend.language.js.tools.babel]] to transpile our code into regular JavaScript that the browser can understand. In most modern React applications, you can add Babel as an [[npm|cs.webdev.frontend.language.js.tools.npm]] dependency to transpile your entire project.

The Babel transpiler will comvert the above JSX syntax into `React.createElement` functions as shown below:

```html
<body>
    <div id="root"></div>
    <script type="text/javascript">
        const rootElement = document.getElementById('root')
        const element = React.createElement('div', {
            className: 'container',
            children: 'Hello World'
        })
        ReactDOM.render(element, rootElement) 
        // As per React 18, this is not the way to attach the app to the root element
    </script>
</body>
```
