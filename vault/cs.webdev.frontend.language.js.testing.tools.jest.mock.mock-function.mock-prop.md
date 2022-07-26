---
id: y3nl3w8z650e2my87odsrk8
title: .mock Property
desc: ''
updated: 1658749382826
created: 1658746844920
---

All mock functions have a `.mock` property which is where the data about how the function has been called, it's return values are stored.

The `.mock` property also tracks the value of `this` for each call, so it's possible to inspect `this` as well.

```js
const myMock1 = jest.fn();
const a = new myMock1();
console.log(myMock1.mock.instances);
// > [ <a> ]

const myMock2 = jest.fn();
const b = {};
const bound = myMock2.bind(b);
bound();
console.log(myMock2.mock.contexts);
// > [ <b> ]
```

The mock members are quite useful in tests to assert:

1. How the functions get called?
2. How the functions get instantiated?
3. What they returned?

e.g.

```js
// The function was called exactly once
expect(someMockFunction.mock.calls.length).toBe(1);

// The first arg of the first call to the function was 'first arg'
// First parameter signifies the first call and the second parameter signifies the 1st argument in that call
expect(someMockFunction.mock.calls[0][0]).toBe('first arg');

// The second arg of the first call to the function was 'second arg'
expect(someMockFunction.mock.calls[0][1]).toBe('second arg');

// The return value of the first call to the function was 'return value'
expect(someMockFunction.mock.results[0].value).toBe('return value');

// The function was called with a certain `this` context: the `element` object.
expect(someMockFunction.mock.contexts[0]).toBe(element);

// This function was instantiated exactly twice
expect(someMockFunction.mock.instances.length).toBe(2);

// The object returned by the first instantiation of this function
// had a `name` property whose value was set to 'test'
expect(someMockFunction.mock.instances[0].name).toEqual('test');

// The first argument of the last call to the function was 'test'
expect(someMockFunction.mock.lastCall[0]).toBe('test');
```
