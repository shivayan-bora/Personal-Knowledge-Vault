
The basic difference lies between how the extend each other:

- Two types:

```js
type X = {
    a: string;
    b: number;
}

type Y = X & {
    c: string;
    d: number;
}
```

- Two interfaces:

```js
interface Person {
    name: string;
    age?: number;
}

interface Guy extends Person {
    occupation: string;
}
```

- One interface and one type:

```js
interface Person {
    name: string;
    age?: number;
}

type X = Person & {
    a: string;
    b: number;
}
```

or

```js
type X = {
    a: string;
    b: number;
}

interface Person extends X {
    name: string;
    age?: number;
}
```
