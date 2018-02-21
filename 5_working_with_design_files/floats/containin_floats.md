### Containing Floats

```html
<div id="columns">
  <div id="primary">
    <h1>Main Content</h1>
  </div>

  <div id="secondary">
    <h3>Sidebar Content</h3>
  </div>
</div>
```

```css
#columns {
  width: 840px;
  padding: 20px;
  margin: 0 auto;
  background: #e0e0e0;
}

#primary, #secondary {
  background: yellow;
}

#primary {
  float: left;
  width: 575px;
}

#secondary {
  float: right;
  width: 245px;
}
```

If the container does not have an element in it that is used to define the height of the container, the float pull elements out of the normal flow of a page.

Elements that are floated or set to `absolute` or `fixed` position are not elements that affect the dimensions of their parents because they are taken out of the normal flow.

For floated elements, we need either some element after the floated elements to clear them, or set the container's `overflow` to a value other than `visible`.

We will create a pseudo element like this:
```css
#columns:after {
  display: block;
  clear: both;
  content: "";
}
```
