### Select Element
`select` are used to create an expandable drop-down list of options, or a boxed list of options.

Two possibe child elements:
- option
- optgroup

Uses the `name` attribute just like other form elements.
Rather than have the value on the `select` element, the value comes from the `option` element.

### Option Element
It is what makes the `select` work.
A `select` element is useless without its `option` elements. Each of these represents a possible value for the select.

Option will use the `value` attribute as the value that is sent with select's name on form submission.

If `value` attr is omitted, the text within the `option` element will be used instead.

Placeholder option:
- Set "Choose one" to a value attribute of ""
- works like the placeholder attribute on text boxes
- The value of select is empty until the user does something with the control

### Optgroup Element
The `optgroup` element has one required attribute, `label` for displaying text at the top of group of options.

You can use two `optgroup` elements to separate the options by label.

```html
<select name="movie">
  <optgroup label="DVD">
    <option>Frozen</option>
    <option>Toy Story 3</option>
  </optgroup>
  <optgroup label="Blu-Ray">
    <option>Monsters, Inc</option>
    <option>WALL-E</option>
  </optgroup>
</select>
```

### Multiple
The `select` element has a `multiple` boolean that allows the user to select more than one option.
The select becomes a list box that allows user to select more than one option.
The select is turned into a scrollable rectangle that displays multiple options at once.

The user then holds either `ctrl` or `command` on their keyboard as they select options.

The `size` attribute can also be used to control how many rows of text will be displayed.

### Textarea element
- Provides user with a multiline version of text input
- `textarea` retain carriage return and newline characters
- The value of `textarea` is not represented with a value attribute
- The value would be the text that is contained within the opening and closing tags of the element.
- If you wanted to pre-fill the `textarea` with a sentence, add that sentence as the text inside of the element.

```html
<textarea name="tweet" rows="5" cols="40">I just got 20% off my first purchase at joesburgers.com! You can too!</textarea>
```

#### Rows and Cols attributes
Only available on the `textarea` element, these two control the horizontal and vertical size of the element.

`width` and `height` can be fine-tuned with CSS.

The row count represents how many rows are visible at a time.

If it exceeds the height, scrollbars appear within the text area.

The default font used for textarea is a monospace font. Font in this category have a pre-set width, the browser is able to determine when to break the text to a new row.

