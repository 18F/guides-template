---
title: Add images
---
There are two ways to add images. First, if you'd like to keep all your images
in a separate directory, create an `images/` directory and put your images inside it.
Otherwise, you can keep an image in the same directory as the page that
references it.

You may want to use [jpegoptim](https://github.com/tjko/jpegoptim) or
[optipng](http://optipng.sourceforge.net/) to optimize your images. On OS X,
both are available via [Homebrew](http://brew.sh/).

Now within your documents, you can reference your images as outlined below and abiding by
the advice in the [Accessibility
Guide](https://pages.18f.gov/accessibility/images/).

If an image is in a separate directory:

```html
<img src="{%raw%}{{site.baseurl}}{%endraw%}/images/images.png" alt="Example of
an included image">
```

If it's in the same directory as the source document, the link should be
relative to the parent directory of the document, specified as `..`:

```html
<img src="../images.png" alt="Example of an included image">
```

<img src="../images.png" alt="Example of an included image">

### Next steps

Click the _Update the Config File_ entry in the table of contents.
