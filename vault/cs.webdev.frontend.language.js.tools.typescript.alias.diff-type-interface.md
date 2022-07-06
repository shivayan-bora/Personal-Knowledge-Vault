---
id: oju1706tjods4vc8vkjdxxk
title: Difference between Types and Interfaces
desc: ''
updated: 1656998914805
created: 1656998696271
---

The basic difference lies between how the extend each other:

- Two types:

```js
type X = {
    a: string;
    b: number;
}

type Y = X & {
    c: string;
    d: number;
}
```

- Two interfaces:

```js
interface Person {
    name: string;
    age?: number;
}

interface Guy extends Person {
    occupation: string;
}
```

- One interface and one type:

```js
interface Person {
    name: string;
    age?: number;
}

type X = Person & {
    a: string;
    b: number;
}
```

or

```js
type X = {
    a: string;
    b: number;
}

interface Person extends X {
    name: string;
    age?: number;
}
```
