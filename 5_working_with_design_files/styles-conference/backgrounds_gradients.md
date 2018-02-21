### Transparent Backgrounds
It's a good idea to provide fallback color, browser support is specifically a problem with Internet Explorer.

We can use two `background-color` properties within a single rule set.

```css
div {
  background-color: #b2b2b2;
  background-color: rgba(0, 0, 0, .3);
}
```
## Adding a background image
Work similarly to background color, however they offer a few additional properties to finesse the images.

The `url()` function will be the background image's path, and rules for creating hyperlink paths apply here.

```css
div {
  background-image: url("alert.png");
}
```
### Background repeat
Will repeat indefinitely, both vertically and horizontally. May be used to change the direction in which a background image is repeated.

```css
div {
  background-image: url("alert.png");
  background-repeat: no-repeat;
}
```

The `repeat-x` value will repeat the background image horizontally, while the `repeat-y` will repeat the background image vertically.

`no-repeat` will tell the browser to not repeat at all.

### Background position
Background images are positioned at the left top corner of an element.
Using the background-position property, we control exactly where the background image is placed.

```css
div {
  background-image: url("alert.png");
  background-position: 20px 10px;
  background-repeat: no-repeat;
}
```

The `background-position` requires two values. If only one value is specified, that value is used for the horizontal offset and vertical offset will default to 50%.

### Shorthand
```css
div {
  background: #b2b2b2 url("alert.png") 20px 10px no-repeat;
}
```
