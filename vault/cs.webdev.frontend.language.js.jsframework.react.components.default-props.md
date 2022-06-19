---
id: 4h57qzdo5dd9itcgyf4uhf6
title: Default Props
desc: ''
updated: 1655626983920
created: 1655626775140
---

You can also define default values for your `props` by assigning to the special `defaultProps` property:

```jsx
// Specifies the default values for props:
Greeting.defaultProps = {
  name: 'Stranger'
};
```

If you are using a Babel transform like `plugin-proposal-class-properties` (previously `plugin-transform-class-properties`), you can also declare defaultProps as static property within a React component class. This syntax has not yet been finalized though and will require a compilation step to work within a browser.

```jsx
class Greeting extends React.Component {
  static defaultProps = {
    name: 'stranger'
  }

  render() {
    return (
      <div>Hello, {this.props.name}</div>
    )
  }
}
```

The `defaultProps` will be used to ensure that `this.props.name` will have a value if it was not specified by the parent component. The [[PropTypes|cs.webdev.frontend.language.js.jsframework.react.components.prop-types]] typechecking happens after `defaultProps` are resolved, so typechecking will also apply to the `defaultProps`.
