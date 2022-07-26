---
id: 02bn2ed7m9s5ji3zx18tlz4
title: afterAll
desc: ''
updated: 1658738454975
created: 1658738188443
---

```js
let animals = [];


beforeAll(() => {
    animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda']
})

afterEach(() => {
    animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda'];
})

afterAll(() => {
    animals = [];
})

describe('animals array', () => {
    it('should add animal to the end of the array', () => {
        animals.push('penguin');
        expect(animals[animals.length - 1]).toBe('penguin');
    })

    it('should add animal to the beginning of the array', () => {
        animals.unshift('monkey');
        expect(animals[0]).toBe('monkey');
    })

    it('should have initial length of 7', () => {
        expect(animals.length).toBe(7);
    })
})
```

After all the test cases are executed, `afterAll` will get executed only once.
