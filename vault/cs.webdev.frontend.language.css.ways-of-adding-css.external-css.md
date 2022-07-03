---
id: 2imke6cnaczoc7zaukrpubq
title: External CSS
desc: ''
updated: 1656860402798
created: 1656860196770
---

```css
/* Selects only h1 in the document */
h1 {
    background: yellow;
}
```

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset='utf8' />
        <title>My Awesome Website</title>
        <!-- rel defines the relationship with current HTML document -->
        <link rel='stylesheet' href='<path-to-css>'/>
    </head>
    <body>
        <h1>My Awesome Website</h1>
    </body>
</html>
```

Can be used in multiple HTML documents.
