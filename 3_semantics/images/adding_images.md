### img element
`<img>` tells the browser to load an image from a separate resource. Two required attributes:

- `src` provides the path the browser must follow.
- It uses the same format as links in the `<a>` tag.
- Can be relative, root relative or absolute.
- Require `alt` attribute to provide text that browser can display.

`alt` attribute describes the content of the image.
Some browsers show a tooltip with the text when you hover your mouse cursor over the image.

Browsers also show the `alt` text when they can't display the image, when download fails or disabled.

Screen readers read aloud for people with vision problems, use `alt` attribute to tell the user about image content.

Search engines also use `alt` to index images.
<img> tag is self-closing.

### Figure and Figcaption

The `<figure>` designates an item as representation of information. The tag encloses some media that illustrates the surrounding context.

Only needed if you want to include a caption for the image.
