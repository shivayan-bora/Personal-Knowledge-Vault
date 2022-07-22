---
id: rz0jgrv50x5xeziioucixeo
title: Radio
desc: ''
updated: 1658382679669
created: 1658380336785
---

Radio buttons are used where you'd want one answer out of a choice of multiple answers.

```html
<label>
    <input type='radio' id='indoor' name='indoor-outdoor' value='indoor'>Indoor
</label>
<label>
    <input type='radio' id='outdoor' name='indoor-outdoor' value='outdoor'>Outdoor
</label>
```

To make sure one option deselects automatically when we select the other option, we need to add the `name` attribute to the radio options with the same value.

When we submit the form, if we don't add a `value` attribute, it will submit the form with values as `indoor-outdoor=on` which isn't very useful. Hence we need to add a `value` attribute with an appropriate value. e.g. in this case, we would have, `indoor-outdoor=indoor` or `indoor-outdoor=outdoor`.

`checked` is used to check a Radio Button by default initially.
