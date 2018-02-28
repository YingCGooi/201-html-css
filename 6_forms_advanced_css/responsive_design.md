## Responsive Web Design

## Overview
Responsive web design aims to develop websites that work on every device and every screen size.

- Focused around providing an intuitive experience for everyone.
- aims to create a natural user experience

## Responsive vs Adaptive vs Mobile
Responsive means to react quickly and positively to any change.
Adaptive means to be easily modified for a new purpose.

Responsive designs - websites fluidly change based on many factors
Adaptive websties - built to a group of preset factors.

### Flexible Layout
- Practice of building the layout of a website with flexible grid, capable of resizing to any width.
- use relative length units, as percentages or `em` units. Used to declare property values such as `width`, `margin` or `padding`

`vmin`
- minimum of the viewport's height and width

`vmax`
- maximum of the viewport's height and width

Flexible layouts do not advocate the use of fixed measurement units. The reason is that the viewport height and width continually change from device to device.

Formula to identify proportions of a flexible layout:

```
target-width / parent-element-width = relative-width
```

## Media Queries
- Built as an extension to media types commonly found when targeting and including styles
- Provide the ability to specify different styles for individual browser
- The width and viewport for device orientation
- Apply uniquely targeted styles

### Initializing Media Queries
- using the `@media` rule inside of an existing style sheet
- importing a new style sheet using `@import` rule
- or by linking to a separate style sheet from within the HTML document
- recommeded to use the `@media` rule inside of an existing style sheet

```css
/* @media Rule */
@media all and (max-width: 1024px) {
  ...;
}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {

}
```

Each media query may include media type followed by one or more expressions.
Common media types include:
- all
- screen
- print
- tv
- braille

Should a media type not specified, it will default to screen.

When a media feature and value allocate to true, the styles are applied.

If the media feature and value allocate to false the styles are ignored.

### Logical Operators
`and`, `not` and `only` help build powerful expressions

Using the `and` logical operator allows an extra condition to be added, making sure that a browser or devices does both `a, b, c`

The example selects all media types between 800 and 1024 pixels wide.

```css
@media all and (min-width: 800px) and (max-width: 1024px) {}
```

_
The `not` logical operator negates the query. In the example below the expression applies to any device thatdoes not have a color screen.
```css
@media not screen and (color) {}
```

The below expression selects only screens in a portrait orientation that have a user agent capable of rending media queries.

```css
@media only screen and (orientation: portrait) {}
```

### Height and Width Media Features
- Can be prefixed with `min` or `max` qualifiers, building a feature such as `min-width` or `max-width`

The `height` and `width` features are based off the height and width of the viewport rendering area. Values for height and width may be any length unit, relative or absolute.

```css
@media all and (min-width: 320px) and (max-width: 780px) {}
```

Most commonly features include `min-width` and `max-width`, these help build responsive websites on desktops and mobile devices.

### Using minimum & maximum prefixes
`min` and `max` can be used on a few media features.
The `min` indicates a value of `greater than or equal to` while the `max` prefix indicates a value of `less than or equal to`

Using `min` and `max` prefixes avoid any conflict with the general HTML syntax, specifically not using the `<` and `>` symbols.

### Orientation Media Feature
- Determines if a device is in the `landscape` or `portrait` orientation.
- The `landscape` mode is triggered when the display is wider than taller, and the `portrait` mode is triggered when the display is taller than wider.

```css
@media all and (orientation: landscape) {}
```

### Aspect Ratio Media Features
The `aspect-ratio` and `device-aspect-ratio` specifies the `width/height` pixel ratio of the targeted rendering area or output device.

The `min` and `max` prefixes are available to use with the different aspect ratio features, identifying a ratio above or below that which is stated.

The value for the aspect ratio consist of two positive integers separated by a forward slash.

```css
`@media` all and (min-device-aspect-ratio: 16/9) {}
```

There are also `pixel-ratio` media features
- Pixel ratio is great for identifying high definition devices, including retina displays.

```css
@media only screen and (-webkit-min-device-pixel-ratio: 1.3), only screen and (min-device-pixel-ratio 1.3) {}
```

### Resolution Media Feature
The `resolution` specifies the resolution of the output device.
- Measured in pixel density, known as DPI.

```css
@media print and (min-resolution: 300dpi) {}
```

### Identifying Breakpoints
Writing media query breakpoints around common viewport sizes such as 320px, 480px, 768px, 1024px, 1224px is a bad idea.

When building a responsive website it should adjust to an array of different viewport sizes.

Breakpoints should only be introduced when a website starts to break, look weird or experience being hampered.

### Mobile First
- a popular technique
- includes using styles targeted at smaller viewports as the default styles
- then use media queries to add styles as the viewport grows
- A user on a mobile device, commonly using a smaller viewport shouldn't have to load the styles for a desktop only to have them over written with mobile styles later.
- As such, it is a waste of bandwidth
- Mobile first approach advocates designing with the constraints of a mobile user in mind
- Before too long, the majority of Internet consumption will be done on mobile

A breakout of mobile first media queries look a bit like this:

```css
/* Default styles first then media queries */
@media screen and (min-width: 400px)  {}
@media screen and (min-width: 600px)  {}
@media screen and (min-width: 1000px) {}
@media screen and (min-width: 1400px) {}
```

Additionally,downloading unnecessary media assets can be stopped by using media queries.

Avoiding CSS3 shadows, gradients, transforms and animations within mobile styles is a good idea.

```css
/* Default media */
body {
  background: #ddd;
}
/* Media for larger devices */
@media screen and (min-width: 800px) {
  body {
    background-image: url("bg.png") 50% 50% no-repeat;
  }
}

```

### Viewport
Mobile devices do a pretty decent job of displaying website. Sometimes they could use a little assistance around identifying the `viewport` size and resolution of a website.

```html
  <meta name="viewport" content="width=device-width" />
```

Apple invented the `viewport` meta tag.

### Viewport Height & Width
Using the `viewport` meta tag with either the `height` or `width` values will define height or width of the viewport respectively.

Each value accepts either a positive integer or keyword.
`device-height` value is accepted for the `height` property.
`device-width` value is accepted for the device width.
Using these keywords will inherit the device's default height and width value.

### Viewport scale
To control how a website is scaled on a mobile device, use the `minimum-scale`, `maximum-scale`, `initial-scale` and `user-scalable` properties.

The `initial-scale` should be set to 1, this defines the ratio between the device height, while in portrait orientation and the viewport size.

When a device be in landscape mode this would be the ratio between the device width and the viewport size.

Values for `initial-scale` should always be positive integer between 0 and 10.

### minimum and maximum scale
The `minimum-scale` and `maximum-scale` determine how small and how large a viewport may be scaled.
When using `minimum-scale` the value should be a positive integer lower than or equal to the `initial-scale`.

These values should not be set to the same value as the `initial-scale`, this would disable any zooming, which can be accomplished instead by using the `user-scalable` value.

Setting `user-scalable` value to `no` will disable any zooming. Alternatively setting the `user-scalable` value to `yes` will turn on zooming.

### Viewport Resolution
The `target-densitydpi` viewport accepts a handful of values including `device-dpi` , `high-dpi`, `medium-dpi`, `low-dpi` or an actual DPI number.

Using the `target-densitydpi`viewport value is rare, but extremely helpful when pixel by pixel control is needed.

```css
<meta name="viewport" content="target-densitydpi=device-dpi" />
```

### Flexible Media
Images, videos and other media types need to be scalable, changing their size as the size of the viewport changes.

One way to make media scalable is using `max-width` property of 100%.

```css
img, video, canvas {
  max-width: 100%;
}
```

### Flexible Embedded Media
Unfortunately the `max-width` property doesn't work well for all instances of media.

There is a workaround for third party websites who use iframes.

The embedded element needs to be absolutely positioned within a parent element.

The parent element needs to have a `width` of `100%` so that it may scale based on width of the viewport.
Also needs to have a `height` of `0` to trigger the `hasLayout` mechanism within Internet Explorer.

Padding is then given to the bottom of parent element.
