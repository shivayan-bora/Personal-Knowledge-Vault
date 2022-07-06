---
id: t0d3zvjj1iral5yg7ejib70
title: Id
desc: ''
updated: 1657040807191
created: 1657034660354
---

This can be used in the following manner:

```html
<style>
    #top-header {
        color: blue;
    }
</style>
<h1 id='top-header'>Hello World</h1>
```

Although the browsers don't enforce it, but we should give every element a unique id if needed or we must use the ids at most for one element. With [[cs.webdev.frontend.language.html]] and CSS you can get away with putting the same id in two different elements. However, when [[cs.webdev.frontend.language.js]] comes into picture, it can become quite dicey. It's an agreed upon standard to use ids only once.

Also, if there are conflicting styles, ids are given more preference (specificity) over classes.

Also, using ids give some performance benefits as the HTML are stored as a hastable with the ids as keys which allows for quicker access to the element. However, it's not much important to consider.
