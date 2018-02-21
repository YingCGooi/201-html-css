### Floats and page layout
There are cases where `inline` or `inline-block` may not be the best solution. This is where floating elements comes into play.

Floating tells the browser to only take up as much width as is needed.

If there's room left over within the row, the next element will take up that space.

We can send an element to the left or right of the container. Two elements that are floated in a row will touch.

```html
<body>
  <div id="primary">
    <h1>Main Content</h1>
  </div>

  <div id="secondary">
    <h3>Sidebar Content</h3>
  </div>
</body>
```

```css
body { background: #e0e0e0; }

#primary {
  float: left;
  width: 65%;
  background: yellow;
}

#secondary {
  float: left;
  width: 25%;
  background: yellow;
}
```

In order to add space between them, we could either add margins or change the secondary column to float right, leaving the remaining space empty. This way, we don't have to recalculate the margin.

If the total width of the float elements exceed the parent element, the secondary element gets pushed below the primary column.

```css
body { background: #e0e0e0; }

#primary {
  float: right;
  width: 65%;
  padding: 25px;
  background: yellow;
}

#secondary {
  float: left;
  width: 25%;
  padding: 25px;
  background: yellow;
}
```
We can add `box-sizing` to have padding taken into account, also moving some of the common styles into a separate CSS block.
