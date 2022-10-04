
In [[HTML|cs.webdev.frontend.language.html]], we'd pass a string of [[CSS|cs.webdev.frontend.language.css]]:

```html
<div style="margin-top: 20px; background-color: blue;"></div>
```

In React, however, we'll pass an object of CSS:

```jsx
<div style={{marginTop: 20, backgroundColor: 'blue'}} />
```

In terms of React, `{{}}` is a combination of JSX expression and an object expression. These properties are `camelCased` rather than `kebab-cased`. This matches the style property of [[DOM|cs.webdev.frontend.language.js.dom]] nodes which is a [[CSSStyleDeclaration|cs.webdev.frontend.language.js.cssstyledeclaration]] object.
