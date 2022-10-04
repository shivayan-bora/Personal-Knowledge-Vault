
It's a self closing tag and an inline element to put images into it. You can specify the width and height of an image directly into the HTML tag but it's not a good standard to do it that way. It's better to use CSS for this purpose.

```html
<img src='<some-img-url>' alt="<some-alternate-text-to-display-if-image-can't-be-loaded>"/>
```

1. `src`: Source of the image
2. `alt`: Alternate text in case the image can't be rendered and specifically helpful for accessibility readers. It also enables good SEO as search engines know what this image is all about.
