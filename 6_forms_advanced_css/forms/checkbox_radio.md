## Checkbox and Radio Inputs
Checkboxes are simply to toggle a value on or off. Any number of checkboxes can be checked.

Radios are a way to visually display all options for particular input name, allowing user to pick which is desired.
When one option from the group is checked, the other previously activated option is deactivated.

Example:

```html
<form action="" method="post">
  <fieldset>
    <h2>Hobbies</h2>
    <ul>
      <li>
        <label>
          <input type="checkbox" name="sports" />
          Sports
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="video_games" />
          Video games
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="spoon_collecting" />
          Spoon collecting
        </label>
      </li>
    </ul>

    <h2>Favorite Color</h2>
    <ul>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="red" />
          Red
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="orange" />
          Orange
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="yellow" />
          Yellow
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="green" />
          Green
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="blue" />
          Blue
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="indigo" />
          Indigo
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="favorite_color" value="violet" />
          Violet
        </label>
      </li>
    </ul>
  </fieldset>
</form>
```

Upon submission, values of "on" will be sent for each checked checkbox. However, only one value will be sent for the `favorite_color` radios.

If any one of the radios had a different `name` attribute, it would be part of a different list of radios.

A `value` attribute can be added with whatever value you'd like.

If a checkbox is unchecked or group of radios has no single radio checked, then there will be no data sent for those inputs.

### Checked
A boolean value of `checked` can be added to set a checkbox or one of the radio inputs to be checked.
To disable some browsers (Firefox) from overriding checked attributes on them (based on remembering the state of checkboxes), add the attribute `autocomplete` and set it to `off`.