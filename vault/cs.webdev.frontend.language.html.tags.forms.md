---
id: k3ynixhd60kjku708t0fuq7
title: Forms
desc: ''
updated: 1656857668099
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

`action` is the url path the form tries to talk to.

`submit` is used to submit the form.

`name` is used as a query parameter.

e.g. in this case, itwould be:

`http://www.somewebsite.com/register?user-name=<value-entered-in-the-input-textbox>`
