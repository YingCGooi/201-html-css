### Text Input
The `name` is paired with the `value` entered in and sent to the server. So the server-side code knows what values it received for each input.

Omitting the `name` attribute will exclude the `value` from being sent to the server.

Example - login form submission:
```
email=joe@lindt.com
password=dragon123
```

If the `form` is send through a `GET` method, then:
```
login.html?email=joe@lindt.com&password=dragon123
```

### Placeholder
Placeholders are meant to contain any text that will assist the user in providing a suitable value.

Example - phone number:
```html
<input type="text" name="phone" placeholder="(212) 555-1212" />
```

Placeholder should not be used in place of `label`. If design must be this way, be sure to include `label` elements and hide them with CSS.

### Minlength and Maxlength
They each take a numeric value that restricts the value entered in.
Support for `minlength` is limited.

Example:
```html
<input type="text" name="title" id="title" maxlength="20" placeholder="20 characters max" />
```

### Email Input
Usually trigger the display of a keyboard
