
Consider the following test cases:

```js
let animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda'];

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

The 3rd test case would fail as the tests before that are modifying the `animals` array. To avoid this, we need to reinitialize the array back to it's original state. However, we shouldn't reinitialize the array in each one of the methods as we're repeating code.

Hence we use setup (`beforeAll`, `beforeEach` etc.) or teardown (`afterAll`, `afterEach` etc.) methods to resolve this.
