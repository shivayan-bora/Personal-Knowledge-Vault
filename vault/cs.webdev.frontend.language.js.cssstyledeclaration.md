---
id: q0ahg7jb3pi7xzq422kfwdq
title: CSSStyleDeclaration
desc: ''
updated: 1655633043450
created: 1655632616964
---

The `CSSStyleDeclaration` interface represents an object that is a CSS declaration block, and exposes style information and various style-related methods and properties.

A `CSSStyleDeclaration` object can be exposed using three different APIs:

- Via `HTMLElement.style`, which deals with the inline styles of a single element (e.g., `<div style="...">`).
- Via the `CSSStyleSheet API`. For example, `document.styleSheets[0].cssRules[0].style` returns a `CSSStyleDeclaration` object on the first CSS rule in the document's first stylesheet.
- Via `Window.getComputedStyle()`, which exposes the `CSSStyleDeclaration` object as a read-only interface.
