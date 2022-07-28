---
id: lgzuu1v650d1fy80ycj9ljr
title: Test Block
desc: ''
updated: 1658810699492
created: 1658810636016
---

```js
test('renders learn react link', () => {
  render(<App />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});
```

Similar to [[cs.webdev.frontend.language.js.testing.tools.jest.test-block]] in [[cs.webdev.frontend.language.js.testing.tools.jest]]. We can either use `it` or `test` in this case.
