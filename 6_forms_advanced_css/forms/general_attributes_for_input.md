## General Attributes for the Input Element

### Disabled
- A boolean attribute
- like `novalidate` attribute.
- adding attribute of `disabled` with no value will render the input, but prevent user from interacting it
- rendered as a gray box
- `file`, `submit`, `button`, they are lighter versions and do nothing when clicked.
- used in combination with JS to toggle the ability to edit one or more fields
- useful when you have part of the data a form needs and you want the user to view it before completing the rest of the form

Example:
- Two-step account creation process
- First page takes the user's email address, password and full name
- Once user clicks the link, they are prompted to enter optional information
- we could display the previously entered values in disabled fields to prevent the user from changing them

### Inputmode
- The value of `inputmode` will tell the browser that it's suggested that the keyboard layout be changed to fit a specific format.
- Common ones are `email`, `tel`, `numeric`, `url`.
- Observe how the `inputmode` on your device changes.

Value
`verbatim`: Alphanumeric, non-prose content (username and passwords)
`latin`: Latin-script input in the user's preferred language with typing aids (text prediction enabled). For human to computer communication such as search boxes.

`latin-name` as latin but for human names.
As latin but with more aggressive typing aids.

`latin-prose` as latin but with more agressive typing aids

`full width latin` - as latin prose, but for the user's secondary languages.

`kana` - romaji input, using full width characters, with support for converting to kanji, intended for Japanese text input

`katakana` - intended for Japanese text input

`numeric` - numeric input including keys for the digits 0 to 9, the user's preferred thousands separator charcter, and the charcter for indicating negative numbers. Use `type="number"` attr instead.

`tel` - including asterisk and pound key. Use `type="tel"` attribute instead

`email` - Use `type="email"` attr if possible instead

`url` - Use `type="url"` if possible instead.

### Readonly
- Similar to the `disabled` attribute. Will not work on some inputs, like checkboxes and radios.

### Required
- Prevents the browser from submitting the form until the input has a value.
- Provides a handy pseudo-class in CSS.

### Autofocus
- Boolean attribute
- Browser will put the user's focus on that input when the page first loads
- Can only be placed on one form control per page.

Example:

```html
<input type="text" name="location" id="location" placeholder="Gibsonton, FL" required autofocus/>
```

Note that the `Location` field is selected when you refresh the browser.

### Pattern
Regular expression that can be added to text-style inputs like `search`, `url` and `email`.
The server side of forms should also be validating the user's values. You can add an extra layer of validation by way of the `pattern` element.

This time `pattern` attribute is required and set to accept birthday values that match the pattern of the placeholder for `Birthday`

Example:
```html
<input type="text" name="birthday" id="birthday" placeholder="2/28" pattern="[0-9]{1,2}\/[0-9]{1,2}" />
```

