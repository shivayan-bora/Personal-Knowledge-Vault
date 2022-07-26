---
id: 4uwua6kpq9c0m3f1hshs6pz
title: toBe Vs toEqual
desc: ''
updated: 1658661345470
created: 1658661166396
---

```js
describe("example tests", () => {
    // Fails as {} !== {}
    it("object assignment 1", () => {
        const obj = {}
        expect(obj).toBe({});
    })
    // Passes
    it("object assignment 2", () => {
        const obj = {}
        expect(obj).toEqual({});
    })
});
```

`toEqual` is used to compare equality of objects, arrays etc. whereas `toBe` can be used for primitives.
