---
id: 4lz8g2g6opi2fe0vh2abo3c
title: Mock Function
desc: ''
updated: 1658749760992
created: 1658746081694
---

Mock functions allow you:

1. To test the links between code by erasing the implementation details of a function.
2. Capturing the calls and the parameters passed to the function in those calls.
3. Capturing instances of the the constructor functions when they're instantiated with the `new` keyword.
4. Allow test-time configuration of return values.

We can create mock functions in two ways:

1. Either by creating a mock function to use in test code.
2. Writing a `manual mock` to override a module dependency.

e.g.

```js
const forEach = (items, callback) => {
    for (let i = 0; i < items.length; i++) {
        callback(items[i]);
    }
}

const mockCallback = jest.fn(x => 42 + x);

describe('mock callback', () => {

    beforeEach(() => {
        forEach([0, 1], mockCallback);
    })


    it("The mock function is called twice", () => {
        expect(mockCallback.mock.calls.length).toBe(2);
    })


    it("The first argument of the first call to the function was 0", () => {
        expect(mockCallback.mock.calls[0][0]).toBe(0);
    })

    it("The first argument of the second call to the function was 1", () => {
        expect(mockCallback.mock.calls[1][0]).toBe(1);
    })

    it("The return value of the first call to the function was 42", () => {
        expect(mockCallback.mock.results[0].value).toBe(42);
    })

    it("The return value of the first call to the function was 43", () => {
        expect(mockCallback.mock.results[1].value).toBe(43);
    })
})
```

In case you don't want any logic for a mock function but just have a function that returns some value, you can do the following:

```js
it('mock return', () => {
    const mock = jest.fn();
    mock.mockReturnValueOnce(true);
    const results = mock();
    expect(results).toBe(true);
})
```
