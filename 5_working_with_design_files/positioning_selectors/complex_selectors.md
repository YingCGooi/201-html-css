## Common Selectors
- Type: Identifies an element based on its type, specifically how that element is declared within HTML.
- Class: Identifies an element based on class attribute value, may be reused multiple times per page
- ID: identifies an element based on its ID attribute

## Child Selectors
### Descendant Selector
- Matches every element that follows an identified ancestor
- Does not have to come directly after the ancestor element, may fall anywhere within the ancestor element
- created by spacing apart elements within a selector, creating a new level of hierarchy for each element list
- The `article h2` selector is a descendant selector, only selecting `h2` elements that fall inside of an article element
- so long as it is within the `article` element, it will always be selected
- `h2` element that are outside the `article` will not be selected

```html
<style>
  article h2 {...}
</style>

<h2>...</h2>
<article>
  <h2>This heading will be selected</h2>
  <div>
    <h2>This heading will be selected</h2>
  </div>
</article>
```

### Direct Child Selector
In the event that a direct child needs be selected, but not every instance of the element nested deeply inside, we may used a `>` sign between the parent element and child element within the selector.

`article > p` is a direct child selector. Any `p` element placed outside of an article element will not be selected.

```html
<style>
  article > p {...}
</style>

<p>...</p>
<article>
  <p>This paragraph will be selected</p>
  <div>
    <p>...</p>
  </div>
</article>
```

## Sibling Selectors
Sibling elements are elements that share a common parent, may also need to be selected.

### General Sibling Selector
- Allow elements to be selected based on their sibling elements
- Created using the tilde character
- Between two elements within a selector

The `h2 ~ p` selector is a general sibling selector that looks for `p` elements that share the same parent of any `h2` elements.

In order for a `p` element to be selected it must come after any `h2` element

```html
<style>
h2 ~ p { ... }
</style>

<p>...</p>
<section>
  <p>...</p>
  <h2>...</h2>
  <p>This paragraph will be selected</p>
  <div>
    <p>...</p>
  </div>
  <p>This paragraph will be selected</p>
</section>
```

### Adjacent Sibling Selector
The adjacent sibling will only select sibling elements directly following after another sibling element.The adjacent sibling selector uses a plus character between two elements.
- The first element identifies what the second element shall directly follow

```html
<style>
  h2 + p { ... }
</style>

<p>...</p>
<section>
  <p>...</p>
  <h2>...</h2>
  <p>This paragraph will be selected</p>
  <div>
    <p>...</p>
  </div>
  <p>...</p>
</section>
```

## Attribute Selector
class and ID attribute selectors are extremely powerful but only the beginning.

### Attribute Present Selector
- Identifies an element based on whether it includes an attribute or not
- To select an element based on if an attribute is present or not, include the attribute name in square brackets within a selector
- The square brackets may or may not follow any qualifier, depending on the level of specificity desired

```html
<style>
  a[target] {}
</style>

<a href="#" target="_blank">...</a>
```

### Attribute Equals Selector
To identify an element with a specific exact matching, attribute value the same selector from before may be used.

```html
<style>
  a[href="http://google.com/"] {...}
</style>

<a href="http://google.com/">...</a>
```

### Attribute Contains Selector
When we don't need an exact match, we can use the asterisk `*`. The asterisk should fall just after the attribute name, directly before the equals sign.

```html
<style>
  a[href*="login"] {...}
</style>

<a href="/login.php">...</a>
```

### Attribute begins with selector
Using the circumflex accent `^` within the square brackets between the attribute name and the equals sign will match the value that begins with the matching string within the brackets.

```html
<style>
  a[href^="https://"] {...}
</style>

<a href="https://chase.com/">...</a>
```

### Attribute ends with

```css
a[href=$=".pdf"] {...}
```
### Attribute spaced selector
Use the tilde `~` character within the square brackets of a selector that should be whitespace-separated, with one word matching the exact stated value

```html
<style>
  a[rel~="tag"] {...}
</style>

<a href="#" rel="tag nofollow">...</a>
```

### Attribute Hyphenated Selector
The vertical line `|` character may be used within the square brackets to denote that the attribute value may be hyphen-separated

```html
<style>
  a[lang|="en"] {...}
</style>

<a href="#" lang="en-US">...</a>
```
Summary:
https://learn.shayhowe.com/advanced-html-css/complex-selectors/#pseudo-classes

## Pseudo classes
- Similar to regular classes in HTML, not directly stated within the markup.
- Dynamically populated as a result of users' actions or the document structure.
- Most common is `:hover`

### Link Pseudo-classes
`:link` and `:visited` pseudo-classes define if a link has or hasn't been visited.
The `:visited` pseudo-class styles links that a user has already visited based on their browsing history.

```css
a:link {...}
a:visited {...}
```

### User Action Pseudo-classes

`:hover`
- applied to element when a user moves their cursor over the element
`:active`
- applied to an element when a user engages an element
`:focus`
- applied to when a user made an element the focus point of the page

```css
a:hover {...}
a:active {...}
a:focus {...}
```

### User Interface State Pseudo-classes
`:enabled`
- selects an input that is in the default state of enabled and available for use
`disabled`
- selects an input that has `disabled` attribute tied to it. Many browsers will fade out disabled inputs to inform users that input is not available.

`:checked`
- selects checkboxes or radio buttons that are checked.
`:indeterminate`
-selects checkboxes or radio button that are neither been selected nor unselected.

```css
input:enabled {...}
input:disabled {...}

input:checked {...}
input:indeterminate {...}
```

### Structural & Position Pseudo-classes
Some pseudo-classes are structural, determined based off where elements reside in the document tree.

#### `:first-child, :last-child, :only-child`
:first child will be selected if its' the first child within its parent
:last child will select an element if it's the last element within its parent

The `:only-child` will select an element if it is the only element within a parent.

```html
<style>
  li:first-child {...}
  li:last-child {...}
  div:only-child {...}
</style>
<ul>
  <li>This list item will be selected</li>
  <li>
    <div>This div will be selected</div>
  </li>
  <li>
    <div>...</div>
    <div>...</div>
  </li>
  <li>This list item will be selected</li>
</ul>
```
### `:first-of-type, :last-of-type, :only-of-type`
`:first`

`:first-of-type` will select the first element of its type
`:last-of-type` will select the last element of its type within a parent.
`:only-of-type` will select an element if it is the only of its type within a parent

```html
<style>
  p:first-of-type {...}
  p:last-of-type {...}
  img:only-of-type {...}
</style>

<article>
  <h1>...</h1>
  <p>This paragraph will be selected</p>
  <p>...</p>
  <img src="#"><!-- This image will be selected -->
  <p>This paragraph will be selected</p>
  <h6>...</h6>
</article>
```

#### `:nth-` selectors
All of these pseudo classes are prefixed with `nth` and accept a number of expression inside of the parenthesis.

Using a number outright will count individual elements from the beginning, or end of the document tree and then select one element.

While using an expression will count numerous elements from the beginning or end of the document.

For example:
`li:nth-child(4)` will select the forth item within a list. When using a number outright it must be a positive number.

`li:nth-child(3n)` will identify every third list item within a list, using this equates to 3x0, 3x1, 3x2.

`odd` and `even` may be used. Alternatively,
`2n + 1` and `2n` would do the same.

Using the `li:nth-child(4n+7)` will identify every fourth list item starting with the seventh list item. The results leading to seventh, eleventh, fifteenth and every element that is a multiple of four.

#### `:nth-child(n)` & `:nth-last-child(n)`

```html
<style>
  li:nth-child(3n) {...}
</style>

<ul>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
</ul>
```

`li:nth-child(2n + 3)` will offset the first selected list item by 3, as a result, 3rd and 5th element are selected.

```html
<style>
  li:nth-child(2n+3) {...}
</style>

<ul>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
</ul>
```
The `li:nth-child(-n+4)` selector is identifying the top four list items, leaving the rest unselected.

```html
<style>
  li:nth-child(-n+4) {...}
</style>

<ul>
  <li>This list item will be selected</li>
  <li>This list item will be selected</li>
  <li>This list item will be selected</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>...</li>
</ul>
```

Adding a negative integer before the `n` argument changes the selector again.

```html
<style>
  li:nth-child(-2n+5) {...}
</style>

<ul>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
</ul>
```

The nth-last-child(n) switches the direction of counting.
The `li:nth-last-child(3n+2)` will identify every third list item starting from the second to last.

```html
<style>
  li:nth-last-child(3n+2) {...}
</style>

<ul>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
  <li>...</li>
  <li>This list item will be selected</li>
  <li>...</li>
</ul>
```

#### `nth-of-type` & `:nth-last-of-type`
With similarities of `nth-child` and `nth-last-child`, the exception is they only count elements of their own type.

```html
<style>
  p:nth-of-type(3n) {...}
</style>

<article>
  <h1>...</h1>
  <p>...</p>
  <p>...</p>
  <p>This paragraph will be selected</p>
  <h2>...</h2>
  <p>...</p>
  <p>...</p>
  <p>This paragraph will be selected</p>
</article>
```

Using `:nth-last-of-type(n)` will identify every second paragraph from the end of a parent element starting with the last paragraph.

```html
<style>
  p:nth-last-of-type(2n+1) {...}
</style>

<article>
  <h1>...</h1>
  <p>...</p>
  <p>This paragraph will be selected</p>
  <p>...</p>
  <h2>...</h2>
  <p>This paragraph will be selected</p>
  <p>...</p>
  <p>This paragraph will be selected</p>
</article>
```
#### Target Pseudo-class
Used to style elements when an element's ID attribute value matches the URI fragment identifier.

The fragment identifier within an URI can be recognized by the hash character `#`.

The URL `http://example.com/index.html#hello`
includes fragment identifier of `hello`

When this identifier matches the ID attribute value of element on the page,
`<section id="hello">` the element may be identified and styled using the `:target` pseudo-class.

If user would visit a page with URI fragment identifier of `#hello`, the section with that same ID attribute would be stylized.

```css
section:target {...}
```

```html
<section id="hello">...</section>
```

### Empty Pseudo-class
Allow elements that do not contain children or text nodes to be selected.
Comments, processing instructions, and empty text nodes are not considered children and not treated as such.

Using `div:empty` pseudo-class will identify divisions without any children or text nodes.

Even if the second `<div>` contains a comment, it is not considered to be a child.
The fourth division contains one blank text space. And the last division contains a

`<strong>` child element, thus has been ruled out.

```css
div:empty {...}
```

```html
<div>Hello</div>
<div><!-- Coming soon --></div><!-- This div will be selected -->
<div></div><!-- This div will be selected -->
<div> </div>
<div><strong></strong></div>
```

### Negation Pseudo-class
`:not(x)` is a pseudo-class that takes an argument - to filter out from the selection to be made.

The `p:not(.intro)` selector uses negation pseudo-class.

```css
div:not(.awesome) {...}
:not(div) {...}
```

```HTML
<div>This div will be selected</div>
<div class="awesome">...</div>
<section>This section will be selected</section>
<section class="awesome">This section will be selected</section>
```

## Pseudo-elements
Dynamic elements that don't exist in the document tree.
Only one pseudo-element may be used within a selector at a given time.

### Textual Pseudo-elements
The `:first-letter` will identify the first letter of text within an element, while the `:first-line` will identify the first line of text within an element.

```css
.alpha:first-letter,
.bravo:first-line {
  color: #ff7b29;
  font-size: 18px;
}
```

```html
<p class="alpha">Lorem ipsum dolor...</p>
<p class="bravo">Integer eget enim...</p>
```
### Generated Content Pseudo-elements
The `:before` and `:after` generated content create new inline level pseudo-elements just inside the selected element.

Are used in conjunction with the `content` property to add insignificant information to a page.

`:before` pseudo element creates a pseudo-element before, or in front of the selected element.

`:after` pseudo-element creates a pseudo element after, or behind the selected element.

These pseudo-elements appear nested within the selected element, not outside.

Below the `:after` pseudo-element is used to display the `href` attribute value of anchor links.

```css
a:after {
  color: #9799a7;
  content: " (" attr(href) ")";
  font-size: 11px;
}
```
```html
<a href="http://google.com/">Search the Web</a>
<a href="http://learn.shayhowe.com/">Learn How to Build Websites</a>
```

### Fragment Pseudo-element
The `::selection` fragment pseudo-element identifies part of the document that has been selected by a user's actions.

The selection may then be stylized, however only using `color, backgroun, background-color` and `text-shadow` properties.

`background-image` property is ignore.

#### Single Colon (:) vs Double Colons (::)
Fragment pseudo-elements the double colons were added to differentiate pseudo-classes from pseudo-elements.

When selecting any of the text within the example below, the background will appear orange.

```css
::-moz-selection {
    background: #ff7b29;
}
::selection {
  background: #ff7b29;
}
```
