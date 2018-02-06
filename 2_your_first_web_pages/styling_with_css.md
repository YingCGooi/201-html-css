### Purpose of CSS
HTML-based styling proved unsustainable.
Adding same styles to every page was tedious and error prone.
CCS was emerged from the chaos caused by these problems.

### Properties
CSS consists of selectors - and one or more properties, each has a name and value.
```
color: red;
```

This code tells browser to color the selected element.

The `style` attribute lets you specify a list of CSS properties.

### Font-size property
Lets us change the typeface size, controls the height of the text.
We'll use a measurement known as pixels.

`font-size` is inheritable. It applies to the text in `strong`, `em` and elements as the regular text in that paragraph.

In general, properties that apply to text and colors are inheritable, others are not.

### Style Element
To apply the same properties to more than one element, `style` element, as opposed to attribute isolates your CSS from HTML.

```HTML
<style>
  /* CSS goes here */
</style>
```

### Linking to Styles
Use a `<link>` tag to download CSS. Most developers lets you store CSS in entirely separate file.

### CSS Selector
Selectors are a special syntax for targeting one or more HTML elements. You can also combine selectors.

### ID and class selectors
CSS has other selectors, the two most common filter are the `class` and `id` attributes.

The `id` attribute uniquely identifies a single element. We can use ID to target single element for styling.

The `class` attribute identifies group of elements that have something in common.
Any element can belong to one or more classes.

### Order of precedence
If the browser encounters a property that has same or greater "weight" than the previous selector, the browser uses the new property.
Otherwise the browser ignores the new property value. We call this behavior the cascade.

```CSS
p {
  font-size: 14px;
}

#intro {
  font-size: 24px;
}
```
The `#intro` selector overrides the `p` selector.

If we want to restrict the background color to `strong` elements, but don't want to remove `highlight` class, we can make the selector more specific.
