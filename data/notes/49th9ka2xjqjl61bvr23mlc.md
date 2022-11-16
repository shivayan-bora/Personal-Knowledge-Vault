
```js
let someFunction: Function
```

Like Objects, you can specify the type of a variable as a Function, however, it's not a good standard. We should do the following instead:

```js
let printName: (name: string) => void
```

or

```js
let printName: (name: string): void {
    console.log(name)
}
```

This means that, we have a function `printName` which takes in a parameter `name` which is a `string` and returns `void` i.e. undefined. We can specify other return types also based on what we want.

We can specify `never` as the return type, which implies it never returns anything.
