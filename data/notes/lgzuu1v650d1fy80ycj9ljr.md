
```js
test('renders learn react link', () => {
  render(<App />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});
```

Similar to [[cs.webdev.frontend.language.js.testing.tools.jest.test-block]] in [[cs.webdev.frontend.language.js.testing.tools.jest]]. We can either use `it` or `test` in this case.
