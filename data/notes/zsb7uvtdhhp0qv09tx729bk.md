
In React we create components. Components are basically functions that returns something that's rendereable e.g. more React elements, strings, `null`, numbers etc. They're self-contained pieces of UI that only re-render when their props change.

We can think of the components or in general UI as a function of the state and props.

You can use `div`, `span` etc. HTML tags to create components or create a custom component that contains a bunch of other React elements composed together to form a single component that can be reused anywhere.

All custom React components must start with an uppercase letter for React to be able to recognize it as a custom component.

```jsx
    const Message = ({children}) => {
      return <div class="message">
        {children}
      </div>
    }

    const element = (
      <div className="container">
        <Message>Hello World</Message>
        <Message>Goodbye World</Message>
      </div>
    )

    ReactDOM.createRoot(document.getElementById('root')).render(element)
```

When creating components, we need to make sure a component returns only one element. We might have multiple components nested inside that element but effectively a component can only return one and only one element.
