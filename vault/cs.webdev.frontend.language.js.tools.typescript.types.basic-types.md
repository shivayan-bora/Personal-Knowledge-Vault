---
id: e118qg9lbkwjsp7cnqsl8bj
title: Basic Types
desc: ''
updated: 1656950577046
created: 1656948504451
---

```js
let name: string
let age: number
let isStudent: boolean

// Array of Strings
let hobbies: string[]

// Tuple: Will accept a pair of number and string
let role: [number, string]
```

There's an `any` type which means it can have any type, however, it defeats the purpose of having typescript.

```js
let name: any
```

Like `any`, we also have an `unknown` type which means we don't know yet.

If you want to have a variable that can be either a `number` or a `string`, we can use a union operator (`|`) as follows:

```js
let someVariable: number | string
```
