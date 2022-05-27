---
id: 18d264ditjt7fmerntuu8uz
title: DOM Node Creation
updated: 1653561545497
created: 1653559941694
---

In order to create a UI using JavaScript, we need to do the following:

```html
<body>
    <div id="root"></div>
        <script type="text/javascript">
        const rootElement = document.getElementById('root')
        const element = document.createElement('div')
        element.textContent = 'Hello World'
        element.className = 'container'
        rootElement.appendChild(element)
    </script>
</body>
```
