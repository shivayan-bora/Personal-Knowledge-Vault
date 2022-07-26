---
id: it1gy5g3a73s74fq8uayxjk
title: Test Suite
desc: ''
updated: 1658776718545
created: 1658660983812
---

`describe` can be used to group test blocks together. It can be considered as a test suite.

```js
describe("example tests", () => {
    it('should add 1 + 2 to equal 3', () => {
        const result = sum(1, 2);
        expect(result).toBe(7);
    });

    it("object assignment", () => {
        const obj = {}
        expect(obj).toEqual({});
    })

});
```
