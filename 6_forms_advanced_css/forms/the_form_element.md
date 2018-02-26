## The Form Element
- The parent element for all of the form controls and fieldsets.
- Responsible for instructing the browser what data to send to the server
- where the data will be sent
- the method (how)

### Action and Formaction
`action` is the path the browser will use when sending the form data to the server.

This attribute can be overriden if any `formaction` attributes are used.

```html
<form action="/login" method="post">
  <fieldset>
    <h1>Log In</h1>
    <label for="email">Email address</label>
    <input type="email" name="email" id="email" />
    <label for="password">Password</label>
    <input type="password" name="password" id="password" />
    <div class="actions">
      <input type="submit" value="Login" />
      <button type="submit" formaction="/account/delete">Delete account</button>
      <button type="submit" formaction="/account/password_reset">Reset password</button>
    </div>
  </fieldset>
</form>
```

Using the `formaction` attribute, we have eliminated the need for separate forms and pages to delete your account/request a password reset.

If either of the button with a `formaction` is clicked, the action on the button is used to submit the entire form rather than the form element's `action` attribute.

The server could then be set to ignore password input, instead only using the email to send a password reset message.

### Method
It tells the browser how to send the data to the server. A `get` method makes the browser initiate an HTTP `GET` request, used when nothing is expected to change on the server side.

A `post` method makes the browser intiate an HTTP `POST` request and is used when we are expecting to create or change data on the server.

### The current specification only supports `GET` and `POST` as form methods. 
Rails uses `put` and `delete` methods for updating a record and deleting one.

A hidden element is instead employed to tell the server what method to use when processing the post request.

Just like with the `action` attribute, there is a way of overriding the `method` attribute using button and submit input attributes.

A `formmethod` attribute can be added to either of these two elements.

### ID
The `id` attribute is useful for instances when there are form controls that exist outside of the form element.

The `form` attribute can be added to the element and the value can be set to match with the `form`'s ID attribute.

### Novalidate
- A boolean attribute
- Prevents any checks from being performed on input types (such as email)
- There is a corresponding formnovalidate attribute for buttons and submit inputs

### Autocomplete
- Prevent the browser from strong and using data that was previously entered
- Turn off the autocomplete suggestions
- Most browsers have this attribute set to on
- Works with any input that accepts input from a keyboard, except for the password field.

### Autocapitalize / Autocorrect
- With emails this is a nuisance
- some servers don't ignore case for their email accounts and having your phone correct your email
- `autocorrect` Uses values of on and off
- while `autocapitalize` uses four different values

**Value: Behavior**
none: Completely disables automatic capitalization
sentences: Automatically capitalize the first letter of sentences
words: Automatically capitalize the first letter of words
characters: Automatically capitalize all characters

### Target
- Lets browser know what to do with the contents that are returned by the server
- By default the browser updates the current window or frame
- Have it display the results in a new window or tab
- The parent document if the form is in a frame, or top document if the form happens to be nested within more than one frame.
- The most common frame element

Frames are a new window within the confines of a block element.
The most common frame element is an `iframe` or inline frame element.

These elements are sometimes used with forms to simulate an AJAX request.

If your form is in an iframe and you want the whole page to reload, you would set this attribute to `_parent` or `_top`.

If you want to use a new window or tab, use the value `_blank`

If your target iframe has a name attribute of "result", your target attribute can be set to "result" and its content will be updated.


