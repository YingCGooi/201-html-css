### Static
Default value that all elements have, not counting changes to the `float` property.
Elements are displayed in the way they appear in the markup.

### Relative
Any CSS property given to offset the element in a direction will move it far relative to its current position.

Like `static`-ly positioned elements, they are part of normal flow of the document.

### Offset Properties: Top, Right, Bottom, Left
The example moves all elements on the page with `item` class down to the right for 10px.

```css
.item {
  position: relative;
  top: 10px;
  left: 10px;
}
```

### Absolute
Removes an element from the document layout.
It does not affect where the elements that surround it are placed. It does not conform to its parent container.

If we want an element to absolute position within its parent container, we need to set the parent container with `position: relative`, otherwise the absolutely positioned element is then positioned relative to the `<body>` element.

### Fixed
Setting the element in a position relative to the window edges and leaves it even as user scrolls the page.
