### Sprite Sheets
- An increase in images comes an increase in the number of separate requests that a browser needs to make, slowing down the loading speed
- Sprite sheets are image files that are composed of multiple images
- Reduces the number of HTTP requests, speeding up load times
- The most common method is lining all the images side by side, or on top of each other

Example of battery indicator.
- if we designed a system that updated the state of battery indicator without reloading the page
- a blank would be left if it is still being loaded by the browser

To split the images in CSS:
1. create a fixed width and height for our battery element

```html
<h1>Battery Life Indicator</h1>

<h2>Full</h2>
<div class="battery full"></div>

<h2>Moderate</h2>
<div class="battery moderate"></div>

<h2>Low</h2>
<div class="battery low"></div>

<h2>Empty</h2>
<div class="battery empty"></div>
```

Then we set the sprite sheet to our background image.
```css
.battery {
  width: 64px;
  height: 124px;
  background: transparent url("battery_indicator.png") 0 0 no-repeat;
}
```

To display a different portion of background image, we are going to reposition the background image relative to the top left corner of the element.

```css
.low {
  /* Push it up another 124px */
  background-position: 0 -248px;
}
.empty {
  /* -372px works as well, but because all icons are the same height you can use percentages */
  background-position: 0 100%;
}
```

Percentages work as if moving a background image by X% means it will align the X% point in the image to the X% point in the container.

`50%` means it will align the middle of the image with the middle of the container.
`100%` means it will align the last pixel of the image with last pixel of the container.