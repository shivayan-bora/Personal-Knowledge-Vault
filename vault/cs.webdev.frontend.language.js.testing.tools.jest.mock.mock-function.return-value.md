---
id: zvx7jl1s27r5xpjdg0040ek
title: Return Value
desc: ''
updated: 1658750042108
created: 1658749794913
---

You can specify the return value of a mock function as below:

```js
it('mock return', () => {
    const mock = jest.fn();
    mock.mockReturnValueOnce(true);
    const results = mock();
    expect(results).toBe(true);
})
```

You can also also inject multiple return values as the following.

```js
const myMock = jest.fn();
console.log(myMock());
// > undefined

myMock.mockReturnValueOnce(10).mockReturnValueOnce('x').mockReturnValue(true);

console.log(myMock(), myMock(), myMock(), myMock());
// > 10, 'x', true, true
```

Here, the first call will return `10`, the next one will return `x` and then the next one and all other subsequent calls will return `true`.

Mock functions are also very effective in code that uses a functional continuation-passing style. Code written in this style helps avoid the need for complicated stubs that recreate the behavior of the real component they're standing in for, in favor of injecting values directly into the test right before they're used.

```js
const filterTestFn = jest.fn();

// Make the mock return `true` for the first call,
// and `false` for the second call
filterTestFn.mockReturnValueOnce(true).mockReturnValueOnce(false);

const result = [11, 12].filter(num => filterTestFn(num));

console.log(result);
// > [11]
console.log(filterTestFn.mock.calls[0][0]); // 11
console.log(filterTestFn.mock.calls[1][0]); // 12
```

Most real-world examples actually involve getting ahold of a mock function on a dependent component and configuring that, but the technique is the same. In these cases, try to avoid the temptation to implement logic inside of any function that's not directly being tested.
