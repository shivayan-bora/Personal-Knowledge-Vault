
Check this bug:

```jsx
class Counter extends React.Component {
    constructor(props) {
        super(props);
        this.state = {count: this.props.initialCount};
    }

    increment() {
        // BUG: this.setState is undefined as the this here doesn't point to the component instance
        this.setState(({count}) => ({count: count + 1}));
    }

    render() {
        return (
            <div>
                <button onClick={this.increment}>+</button>
                <div>{this.state.count}</div>
            </div>
        );
    }
}
```

Fix: bind `this` to the component instance in the constructor.

```jsx
class Counter extends React.Component {
    constructor(props) {
        super(props);
        this.state = {count: this.props.initialCount};
        // If you have a lot of handlers, you need to bind them all
        this.increment = this.increment.bind(this);
    }

    increment() {
        
        this.setState(({count}) => ({count: count + 1}));
    }

    render() {
        return (
            <div>
                <button onClick={this.increment}>+</button>
                <div>{this.state.count}</div>
            </div>
        );
    }
}
```

or use arrow functions

```jsx
class Counter extends React.Component {
    constructor(props) {
        super(props);
        this.state = {count: this.props.initialCount};
    }

    // This is called a class field
    increment = () => {
        this.setState(({count}) => ({count: count + 1}));
    }

    render() {
        return (
            <div>
                <button onClick={this.increment}>+</button>
                <div>{this.state.count}</div>
            </div>
        );
    }
}
```

This would be syntactic sugar for:

```jsx
class Counter extends React.Component {
    constructor(props) {
        super(props);
        this.state = {count: this.props.initialCount};
        // This is called a class field
        this.increment = () => {
            this.setState(({count}) => ({count: count + 1}));
        }
    }

    render() {
        return (
            <div>
                <button onClick={this.increment}>+</button>
                <div>{this.state.count}</div>
            </div>
        );
    }
}
```

Also,

```jsx
    constructor(props) {
        super();
        // This will fail as this.props doesn't exist yet as super is the one assigning props
        this.state = {count: this.props.initialCount};
    }
```

This implies, you can move both state and handlers outside of the constructor by using class fields feature in ES6.

These are some of the stuff that we need to learn in JavaScript before learning about React.
