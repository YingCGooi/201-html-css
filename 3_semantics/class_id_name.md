### Classes
- Use the `class` attribute to assign a class.
- Any number of elements may be assigned the same class
- Any element can belong to multiple classes.
- Use names that provide meaning (`teaching-assistant` instead of `yellow-background`)
- has lower specificity than ID, but higher than tag name selectors

### ID
- Applies a unique name to a single element
- no other element should have the same ID

```html
<h1 id="headline">
```

```css
#headline {
  font-size: 200%;
}
```
- use `id` to assign an ID
- each ID must be unique
- use CSS selectors to select elements by ID
- have higher CSS specificity than class selectors

### Names
`name` attribute only applies to forms.
When you submit a form, the browser sends the form data using name/value pairs. Each name comes from the associated form element.

```html
<form method="get" action="...">
  <label for="first-name-field">First name:</label>
  <input type="text" name="first-name" id="first-name-field" />

  <label for="last-name-field">Last name:</label>
  <input type="text" name="last-name" id="last-name-field" />

  <input type="submit" value="Search" />
</form>
```
When the form is submitted, the browser constructs a query string:

```
first-name=Joe&last-name=Jones
```
- use both a `name` and an `id` on form elements that use `for` attribute. They should be identical

- use the `name` attribute to assign a name.
- each name in a form should be unique except:
  - radio buttons that belong to a group
- use descriptive and specific `name` values.
