
`PropTypes` are used to run validation on the `prop` being received by a component. It is used to validate the data type as well as if a particular `prop` is mandatory.

However, `PropTypes` add some runtime overhead resulting in suboptimal performance and hence, they don't run in a production environment.

These days however, people also prefer using [[TypeScript|cs.webdev.frontend.language.js.tools.typescript]] for `prop` validation instead of `PropTypes`.

Adding `PropTypes` to functional components:

```jsx
import PropTypes from 'prop-types'

function HelloWorldComponent({ name }) {
  return (
    <div>Hello, {name}</div>
  )
}

HelloWorldComponent.propTypes = {
  name: PropTypes.string
}

export default HelloWorldComponent
```

**References:**
[TypeChecking with PropTypes](https://reactjs.org/docs/typechecking-with-proptypes.html)
