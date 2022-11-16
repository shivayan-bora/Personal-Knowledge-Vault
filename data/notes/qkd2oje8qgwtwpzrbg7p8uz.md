
If you want to run `beforeAll` or `afterAll` only for one `describe` block, do the following:

```js
let animals = [];


describe('animals array', () => {
    beforeEach(() => {
        animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda'];
    })

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

describe('testing something else', () => {
    it('should return the correct value', () => {
        expect(true).toBe(true);
    })
})
```
