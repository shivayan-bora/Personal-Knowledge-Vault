
This is an additive color model that we use in CSS. Here, the colour begins as black and change as different levels of red, green and blue are introduced.

An easy way to do this is with the CSS `rgb` function.

```css
.box {
    background-color: rgb(red, green, blue);
}
```

Here, each one of the argument corresponds to a specific color in the RGB model. The first one is for red, second one for gree and last one for blue. To add any amount of red, green or blue, we increase the number of the corresponding argument.

Here, 0 is the lowest which would mean there's no corresponding RGB component available i.e. 0% and 255 is the highest number, signifying the highest amount of that particular colour available i.e. 100%.

We can also denote the colour as Hex values with a `#`. Hexadecimal, or base 16 values, go from 0 - 9, then A - F:

0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F

With hex colors, 00 is 0% of that color, and FF is 100%. So #00FF00 translates to 0% red, 100% green, and 0% blue, and is the same as rgb(0, 255, 0).

```css
.green {
  background-color: #007F00;
}
```
