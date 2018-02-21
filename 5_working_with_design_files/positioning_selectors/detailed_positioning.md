## Detailed Positioning
Sometimes more strict control is needed, elements may be positioned using other techniques, including `relative` or `absolute` positioning.

## Containing Floats
Allow elements to appear next to, or apart from, one another.
- Build a natural flow within a layout and allow elements to interact with one another.
- When floated, an element's position is dependent on the other elements

### Problems with Floats
- Involves a parent element that contains numerous floated elements
- page's content will respect the size and placement of the floated children element, but they no longer impact the outer edges of the parent container
- in this event the parent element loses context of exactly what it contains and collapses, giving the parent element a height of 0.

If the nested elements not line up correctly, styling errors may appear.
- The `.box-set` division should have a light gray background
- The background is not seen as all of the elements nested within it are floated.
- the `.box-set` division you'll see it has a height of 0

One way to force containing these floats would be to place an empty element just before the parent elements closing tag, which would need to include the style declaration `clear: both`

Clearing floats this way isn't exactly semantic.

### The Overflow Technique
- Setting the `overflow` property value to `auto` within the parent element will contain the floats.
- This will result in an actual `height` for the parent element, thus including a gray background in our example.

Drawbacks:
- When adding styles or moving nested elements that span outside of the parent, the styled element will be be cut off wherever it lies outside the parent element.

### The Clearfix Technique
The better technique is to use the `clearfix` technique.
A bit more complex but does have better support.

Using the `:before` and `:after` pseudo elements,
we can create hidden elements above and below the parent containing the floats.

- The `:before` pseudo-element is used to prevent the top margin of child elements from collapsing
- It is done by creating an anonymous table-cell element using the `display: table;` declaration
- The `:after` pseudo-element is used to prevent the bottom margin of child elements from collapsing
- also to clear nested floats.

Adding `*zoom` property triggers the `hasLayout` for IE 6 and IE 7.

### Effectively Containing Floats
One common practice is to assign a class to the parent element which includes the floats needing to be contained.

The class name is coined as `group`. The `group` class name can then be applied to any parent element needing to contain floats.

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
  *zoom: 1;
}
```
### Single Pseudo-Elements
When trying to use the clearfix technique with other `:before` and `:after` pseudo-element, the other pseudo-elements may override the clearfix pseudo-elements

Only one `:before` and one `:after` pseudo-element are allowed per element.

### Position Static
Elements by default have the `position` value of `static`.
- They don't accept any specific box offset properties.

### Position Relative
Similar to `static`, the difference is that the `relative` value accepts the box offset properties `top`, `right`, `bottom` and `left`.

These box offset allow the element to be precisely positioned, shifting the element in any direction.

**How Box Offset Properties Work**
`top, right, bottom, left` specify how elements may be positioned.
These offset work on only elements with a `relative, absolute` or `fixed` positioning value.

A `top` value of 20px on a relatively positioned element will push the element 20px from where it was originally place. Switching to `-20px` will pull the element 20px up.

For elements using `absolute` or `fixed`:
- These properties specify the distance between the element and the edges of its parent element.
- For example, using a `top` value of 20px on an absolutely positioned element will push the element 20px down from the top of its relatively positioned parent.
- Switching the `top` value to `-20px` will pull the element 20px up from the top of its relatively positioned parent.
- While the `relative` position does not accept box offset properties, the element still remains in the normal, or static flow of the page.
- The relatively positioned element may overlap or underlap other eleents.

In case that the `top` and `bottom` box offset properties are both declared, the `top` properties will take priority.

Additionally, if both the `left` and `right` box offset properties are declared, priority is given in the direction is `left` for English and `right` for Arabic.

### Position Absolute
- Accept box offset properties.
- Removed from the normal flow of the document
- Elements are positioned directly in relation to their containing parent whom is relatively or absolutely positioned.
- Should a relatively or absolutely positioned parent not present, it will be positioned in relation to the `body` of the page.
- If we set relative positioning on a parent element, any elements within that element will be positioned relative to the parent element. Then, if we set absolute positioning on the child element, we can move it absolutely in relation to the parent element, instead of `<body>`.

Specifying horizontal and vertical offset properties will move the element with those property values in relation to its relatively positioned parent.

An element with a `top` value of `50px` and `right` value of `100px` will position the element 50 pixels down from the top of its relatively positioned parent and 100 px from the right of its relatively positioned parent.

**Priorities**
When an element has a fixed `height` and `width` and is absolutely positioned, the `top` property takes priority should both the `top` and `bottom` offset properties be declared. `left` and `bottom` is given priority based on which language the page is written.

### Position fixed
Using position `fixed` works like that of `absolute`, however the positioning is relative to the browser viewport. It does not scroll with the page.
Elements will always be present no matter where a user stands on a page. Does not work with IE6.

### Fixed Header or Footer
One common use is to build a fixed header, or footer, anchored to one side of a page.

We declare `left`, `right` and `bottom` box offset properties, this allows the `footer` to span the entire width of the bottom of the page.

### Z-index property
Elements with the higher `z-index` will appear on the top regardless of its placement in the DOM.

You must first apply a `position` value of `relative`, `absolute` or `fixed`.
