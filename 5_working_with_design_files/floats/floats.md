### Positioning with Floats
The `float` property allows us to take an element, remove it from normal flow of a page and position it to the left or right of its parent element.

An `<img>` element floated will allow the paragraphs to wrap around the image as necessary.

When used on multiple elements, we can create layout by floating elements directly next to or opposite each other.

### In Practice
When an element is floated, it will float all the way to the edge of its parent element.

When we float an element, we take it out of the normal flow. This causes the width to default to the width of the content within it.

It can be corrected by adding a fixed `width` property value to each column.

To prevent floated elements from touching one another, we can use the `margin` property to create space between elements.

### Floats may change an element's display value
An element is removed from the normal flow of a page, it may change an element's default `display` value. The `float` property relies that an element having a `display` value of `block`.

The `<span>` inline-level element ignores any `height` or `width` property values.

Should that inline-level element be floated, its `display` will change to `block`, then may accept height and width properties.

### Clearing & Containing Floats
The `float` property was originally designed to allow content to wrap around images.
An image could be floated, all of the content surrounding that image could then naturally flow around it.

Occasionally the proper styles will not render on an element sitting next to or is a parent element of a floated element.

When an element is floated, it is taken out of the normal flow of the page an styles of elements around that floated element can be negatively impacted.

Sometimes unwanted content begins to wrap around a floated element. Removing an element from the flow of the document allows elements around element to wrap and consume any available space.

### Containing floats
Containing floats does help to ensure that all our styles will be rendered properly.

To contain floats, the floated elements must reside within a parent element.

```css
.group:before,
.group:after {
  content: "";
  display: table;
}
.group:after {
  clear: both;
}
.group {
  clear: both;
  *zoom: 1;
}
```
