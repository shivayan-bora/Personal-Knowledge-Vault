---
id: xlu52erornkgek7w497mweg
title: Objects
desc: ''
updated: 1656998618720
created: 1656950025260
---

```js
let person: Object
```

This can be used to specify the type as Object but it's not a good standard. Instead we use `types` as follows:

```js
type Person = {
    age?: number;
    name: string;
}

let person: Person = {
    name: 'Shivayan',
    age: 32
}
```

`?` here implies an optional parameter.

This `type` specifies an [[cs.webdev.frontend.language.js.tools.typescript.alias]] of an object.

We can have an array of objects also:

```js
let persons: Person[]
```

We can also use `interface` as well.
