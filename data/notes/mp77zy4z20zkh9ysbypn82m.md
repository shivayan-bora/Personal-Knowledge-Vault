
![Differences](/assets/images/2022-07-26-10-24-14.png)

- `findBy`, `getBy`, `queryBy` are used to fetch only one element but `findAllBy`, `getAllBy`, `queryAllBy` return an array of elements.
- `getBy` and `getAllBy` will throw an error if no match is found and they can't be used asynchronously.
- `findBy` and `findAllBy` is similar to it's `get` counterpart, however, it can be used asynchronously. What that means is, if we have an element that renders whenever there's a successful API call, we need to use `find`.
- `queryBy` and `queryAllBy` is similar to it's `get` counterpart with the only difference that, when we don't get a match, we don't get an error.
