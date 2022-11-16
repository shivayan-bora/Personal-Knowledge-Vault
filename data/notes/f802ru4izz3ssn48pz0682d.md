
```js
let animals = [];


beforeAll(() => {
    animals = ['elephant', 'lion', 'tiger', 'bear', 'zebra', 'giraffe', 'panda']
})

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

Before any of the test cases are executed, `beforeAll` will get executed only once.
