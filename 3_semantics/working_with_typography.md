## Working with Typography

### Typeface vs font
Typeface is what we see. Artistic impression of how text looks, feel and reads.

A font is a file that contains a typeface.

A typeface is a desing of the text - how it looks feels and reads.


### Changing font properties
There are two categories of font properties:
- font-based
- text-based

### Font Family
Used to declare which font, as well as which fallback or substitute fonts.

The first declared font, is the primary font choice. Alternative fonts are declared after it in order of preference from left to right.

Font name of two or more words need to be wrapped in quotation marks.
The last font should be a keyword value, either `san-serif` or `serif`.

```css
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

`Helvetica Neue` is the preferred font to display. If this font is unavailable, the next font `Helvectica` will be used.

### Font Size
Provides the ability to set the size of text, usind pixels, em, percentages, point, or `font-size` keywords.

### Font Style
- Accepts four keyword:
- normal, italic, oblique and inherit

Most commonly used are `italic` and `normal`.

### Font Variant
Occasionally text will need to be set in small caps.
The typical values are `normal` and `small caps`.

```css
.firm {
  font-variant: small-caps;
}
```
### Font Weight
Values include `normal, bold, bolder, lighter` and `inherit`

We can set the `font-weight to bold`.

The numeric values `100, 200, 300, 400, 500, 600, 700, 800 and 900` pertain to multi-weight typefaces.

The keyword `normal` maps to `400` and the keyword `bold` maps to 700.

### Typeface weights
We need to check and see whether the typeface we are using comes in the weight.
Attempting to use a weight that's not available will cause those styles to default to the closest value.

### Line Height
The distance between two lines of text (referred to as leading) is declared using `line-height`.

As a general rule, the `line-height` should be set to around one and a half times the `font-size` property value.

Line height may also be used to vertically center a single line of text within an element.

```css
.btn {
  height: 22px;
  line-height: 22px;
}
```
This technique can be used with buttons, alert messages and other single-line text blocks.

### Shorthand font properties
A forward slash is needed between the `font-size` and `line-height` property values.

When using this shorthand notation, every value is optional, except:
- font-size
- font-family

```css
html {
  font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

## Applying Text Properties
Decision on alignment, decoration, indent, transform, and space text can be made with text properties.

### Text Align
Has five values:
- left
- right
- center
- justify
- inherit

```css
p {
  text-align: center;
}
```

should not be confused with `float`.
The `text-align` values `left` and `right` will align text within an element to the left or right, wheareas the `float` will move the entire element.

### Text Decoration
- Provides various ways to spruce up text
- Accepts keyword values of `none, underline, overline, line-through and inherit`

```css
.note {
  text-decoration: underline;
}
```

### Text indent
Can be used to indent the first line of text within an element.

All common length are available, including pixels, points, percentages and so on.

```css
p {
  text-indent: 20px;
}
```

positive values will indent text outward, negative inward

### Text Shadow
`text-shadow` allows us to add a shadow.
Takes four values, all listed one after other from left to right.

First three values are lengths, the last value is color.

```css
/* text-shadow: [horizontal offset], [vertical offset], [blur radius], [color] */

p {
  text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);
}
```

Multiple text shadows can be chained together using comma-separated values, adding more than one shadow to text.

### Box shadow
Since `text-shadow` places a shadow on the text of an element, we can use `box-shadow` to place a shadow on the element as a whole.

`box-shadow` property accepts the same values as `text-shadow`

The fourth value is the spread. The spread will expand the shadow larger than the size, as a negative length value the spread will shrink.

May include an optional `inset` value - place the shadow directly inside the element.

### Text Transform
While the `font-variant` looks for an alternative variant of a typeface, the `text-transform` will change the text inline without the need for alternative typeface.

Only accepts:
- none
- capitalize
- uppercase
- lowercase
- inherit

### Letter Spacing
We can adjust the space between letters on a page. A positive length will push letters farther apart, a negative length value will pull letters closer together.

### Word Spacing
Word-spacing accepts the same length values and keywords as the letter-spacing property.
`word-spacing` applies those values between words.

### Using Web-safe Fonts
No matter what device is browsing our site, the font will render properly.
These fonts have become known as "web-safe fonts"

- Arial
- Garamond
- Lucida Sans, Lucida Grandem, Lucida
- Tahoma
- Trebuchet
- Courier New, Courier
- Georgia
- Palatino Linotype
- Times New Roman
- Verdana

First we use `@font-face` at rule to identify our font's name via `font-family`, as well as the source of our font.

```css
@font-face {
  font-family: "Lobster";
  src: local("Lobster"), url("lobster.woff") format("woff");
}

body {
  font-family: "Lobster", "Comic Sans", cursive;
}
```
