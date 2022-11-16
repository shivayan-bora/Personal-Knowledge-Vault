
Tests have to be inside of a test block like `it` or `test` etc.

```js
it('should add 1 + 2 to equal 3', () => {
    const result = sum(1, 2);
    expect(result).toBe(7);
});
```
