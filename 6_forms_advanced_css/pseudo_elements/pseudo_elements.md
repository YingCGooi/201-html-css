### Pseudo Elements
You can use a before and after pseudo element as if they were elements that are already present in the HTML.

Example:

```html
<h1>Groceries</h1>
<ul>
  <li>Wheat bread</li>
  <li>eggs</li>
  <li>milk</li>
</ul>
```

```css
ul {
  padding-left: 0;
  list-style: none;
}

ul li:before {
  content: "*";
}
```

This will put an asterisk before the text content within each `<li>`
The before and after pseudo elements are elements that occur inside the element.

Putting bullet characters before and after our list item text:
```css
ul {
  padding-left: 0;
  list-style: none;
}

ul li:before,
ul li:after {
  content: "\2022";
}
```

Pseudo elements default to inline elements.
Could be changed to block or inline-block, have margin, border, background properties.

Note:
Either double colons `::` or single colon `:` word for pseudo elements. `::` is added in CSS3 to distinguish `pseudo-classes` from `pseudo-elements`

There are `pseudo-elements` that only works with `::`.

