## Type

The default type is text.
- Simple boxes you can enter any Unicode characters you want in for the value
- Do not have a maximum or minimum length by default

Other types:
Value
- Button: Push button with no default behavior
- Checkbox: You must use the value attribute to define the value, use the checked attribute to indicate whether the item is selected. The third state is indeterminate (draws a horizontal line across the checkbox). This state can only be set via JS.
- color: Control for specifying color. A color picker's UI has no required features - other than accepting simple colors as text
- date: control for entering a date (year, month, day with no time)
- datetime-local - control for entering a date and time with no time zone.
- email: field for editing an e-mail address. Input is validated to contain either empty string or single valid email address.
- file: lets user select a file, use the accept attribute to define the types of files that the control can select.
- hidden: control not displayed, but values is submitted to the server
- image: graphical submit button. Use the `src` attribute to define the source of image and the alt attribute to define alternative text
- month: control for entering month and a year, no time zone.
- number: control for entering floating point number
- password: a text field which value is censored. maxlength optional
- radio: you must use the value attr to define the value submitted by this item. `checked` attr can indicated whether tis item is selected. Radio buttons that have the same value for the name attribute are in the same "radio button group". One radio button in a group can be selected at one time.
- range: control for entering a number (exact value is not important)
- `min:0` `max:5`
- `value: min + (max-min)/2` or min if max is less than min. `step: 1`
- url: validated to contain either the empty string or valid absolute URL before submitting. Line breaks or leading/trailing whitespace are automatically removed from the input value. The `:valid` and `:invalid` CSS pseudo-class are applied.
- week: a control for entering a date consisting of a week-year number and a week number with no time zone.

