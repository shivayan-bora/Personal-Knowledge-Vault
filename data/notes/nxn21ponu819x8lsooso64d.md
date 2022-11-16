
Take a look at the following code example:

```jsx
function message({children}) {
    return <div className='message'>{children}</div>
}

const helloElement = React.createElement('div', {children: 'Hello World'})

const element = (
    <div className='container'>
        {helloElement}
        {message({children: 'Goodbye World})}
    </div>
)

ReactDOM.render(element, document.getElementById('root'))
```

When we take a look at the component tree in the React Devtools, we can see the following:
![createElement vs Returning Elements](/assets/images/2022-06-18-23-30-45.png)

We can see that a new React Element is created when we call `React.createElement` but the same doesn't happen when we directly return a component as done in `message` function. So there's some difference on how React manages elements created via `React.createElement` as compared to calling a function that returns an element.
