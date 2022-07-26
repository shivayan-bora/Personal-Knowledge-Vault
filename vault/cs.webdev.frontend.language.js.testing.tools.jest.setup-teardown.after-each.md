---
id: 8rr69285bf9q7o0szl7m2sv
title: afterEach
desc: ''
updated: 1658737935371
created: 1658737865416
---

```js
let animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda'];


afterEach(() => {
    animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda'];
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

This will run the statements inside the `afterEach` function after each test case is executed.
