---
id: 600wuvn8o8g5q3wsx0de5sz
title: Usage
desc: ''
updated: 1653561559893
created: 1653560828378
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
