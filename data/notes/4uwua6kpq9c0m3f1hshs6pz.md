
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
