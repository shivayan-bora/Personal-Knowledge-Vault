---
id: k3ynixhd60kjku708t0fuq7
title: Forms
desc: ''
updated: 1658382773405
created: 1656850443031
---

```html
<form method='GET' action='/register'>
    <input type='text' name='user-name'/>
    <input type='submit' />
</form>
```

Form is used to submit data to the backend.

The `method` attribute defines what HTTP method it uses to talk with the backend.

`action` is the url path the form tries to talk to. This is where the form sends it's data to.

`submit` is used to submit the form. A button inside a form submits the form by default but we can be specifically set that button to submit the form by specifying, `type='submit'`.

`name` is used as a query parameter.

e.g. in this case, itwould be:

`http://www.somewebsite.com/register?user-name=<value-entered-in-the-input-textbox>`

In forms, everything exists in a `name=value` pair. It's recommended to give those attributes to all the form elements that needs it.
