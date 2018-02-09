### Intro
Forms:
- enables websites to capture information from users and to process requests
- offer controls for every imaginable use of an application
- forms can request small amount of information
- or large amount of info (entire job application)

### Initializing a form
Use a `<form>` element.
```html
<form action="/login" method="post">
</form>
```
The action attribute contains URL to information included within form will be sent for processing.
The `method` is the HTTP method browsers should use to submit form data.

### Text fields
`<input>` is used to obtain text from users
uses `type` attribute to determine what information to be captured.
`name` attribute is used as the name of the control, which can help the server identify the input.

`<input type="text" name="username">`

The `<input>` element is self-contained, only uses one tag and does not wrap any other content.

Many `type` attribute values were introduced in HTML5.
- color
- email
- range
- url
- number
- time

```html
<input type="date" name="birthday">
<input type="time" name="game-time">
<input type="email" name="email-address">
<input type="url" name="website">
<input type="number" name="cost">
<input type="tel" name="phone-number">
```

The different `type` attribute values give iOS7's form control a different look.

### Textarea
`<textarea>` differs from the `<input>` element, as it does not accept any `type` attribute.
Has start and end tags. Text area can accept larger passages of text spanning multiple lines. The `name` attribute is used.

```html
<textarea name="comment">Add your comment here</textarea>
```
`cols` for width and `rows` for height in terms of number of lines of visible text.

### Multiple Choice Inputs & Menus

#### Radio Buttons
Permit users to select one option only.
The `<input>` element is used with a `type` attribute value of radio.

Each radio button element should have the same `name` attribute value.

To preselect a radio button, we use the Boolean attribute 'checked'

```html
<input type="radio" name="day" value="Friday" checked> Friday
<input type="radio" name="day" value="Saturday"> Saturday
<input type="radio" name="day" value="Sunday"> Sunday
```
#### Check Boxes
Check boxes allow users to select multiple options.
The options are tied to one control name.

```html
<input type="checkbox" name="day" value="Friday" checked> Friday
<input type="checkbox" name="day" value="Saturday"> Saturday
<input type="checkbox" name="day" value="Sunday"> Sunday
```

#### Drop-down lists
Provides the format for long list of choices.
Use the `<select>` and `<option>` elements.

The `name` attribute resides on the `<select>` element. `value` attribute resides on the `<option>` elements.

```html
<select name="day">
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>
```

#### Multiple selections
The boolean multiple allows user to choose more than one option from the list.
The size of the `<select>` element can be controlled using CSS, should be adjusted appropriately.

Worthwhile to inform users to choose multiple options, as they'll need to hold down Shift key while clicking.

```html
<select name="day" multiple>
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>
```

### Form Buttons
Allows user to submit input.

#### Submit Input
The submit input is created using `<input>` element with a `type` attribute value of submit.
```html
<input type="submit" name="submit" value="Send">
```

#### Submit Button
The `<input>` submit button is self-contained and cannot wrap any other content. If more control over the structure and design - the `<button>` element may be used.

`<button>` includes opening and closing tags, which may wrap other elements, it acts as if it has a `type` attribute value of `submit`.

```html
<button name="submit">
  <strong>Send Us</strong> a Message
</button>
```

### Other Inputs
#### Hidden Input
Typically used for tracking codes, keys, other information.
This information is not displayed  on the page, can be found by viewing the source code of a page, putting sensitive information is not recommended.

```html
<input type="hidden" name="tracking-code" value="abc-123">
```

#### File Input
```html
<input type="file" name="file">
```

### Organizing Form Elements
Users need to understand what is being asked of them and how to provide requested information.

#### Label
Provides captions or headings for form controls.
Labels should include text the describes the inputs.

Labels may include a `for` attribute.
The value of the `for` attribute should be the same as the value of the `id` attribute on the corresponding form control.

If the `for` attribute matches `id`, the form allows users to click on the `<label>` element to bring focus to form control.

`<label>` element may wrap form controls

```html
<label>
  <input type="radio" name="day" value="Friday" checked> Friday
</label>
<label>
  <input type="radio" name="day" value="Saturday"> Saturday
</label>
<label>
  <input type="radio" name="day" value="Sunday"> Sunday
</label>
```

### Fieldset
Fieldsets group controls an label into organized sections.
Much like a `<section>`, `<fieldset>` is a block-level element that wraps related elements, within a `<form>` element.

```html
<fieldset>
  <label>
    Username
    <input type="text" name="username">
  </label>

  <label>
    Password
    <input type="text" name="password">
  </label>
</fieldset>
```

### Legend
Legend provides a caption or heading for the `<fieldset>` element.
The markup should include `<legend>` element directly after the opening `<fieldset>` tag.

```html
<fieldset>
  <legend>Login</legend>
  <label>
    Username
    <input type="text" name="username">
  </label>
  <label>
    Password
    <input type="text" name="password">
  </label>
</fieldset>
```

### Form & Input Attributes
#### Disabled
Turns off an element or control, so that it is not available for interaction.

Applyng `disabled` to `<fieldset>` will disable all the form controls. If the `type` attribute has a `hidden` value, the `hidden` Boolean attribute is ignored.

```html
<label>
  Username
  <input type="text" name="username" disabled>
</label>
```
#### Placeholder
Provides hint or tip within form control of `<input>` or `<textarea>` element.

```html
<label>
  Email address
  <input type="email" name="email-address" placeholder="name@domain.com">
</label>
```

Differences between `placeholder` and `value`
- `value` attribute stays in place when a control has focus, unless user manually deletes it

#### Required
Must contain a value upon being submitted to the server.
Should an element not have a value, an error message will be displayed.
Error message styles are controlled by the browser.
Invalid elements can be styled using the `:optional` and `:required` CSS pseudo-classes.

```html
<label>
  Email Address
  <input type="email" name="email-address" required>
</label>
```
