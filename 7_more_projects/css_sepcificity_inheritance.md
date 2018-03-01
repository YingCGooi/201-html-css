The notion of 'cascade' is at the heart of CSS. It determines which properties will modify a given element.

The cascade has assigned a weight to each rule, and weight deteremines which rule takes precedence, when more than one applies.

###b Importance
Stylesheets have a few different sources:
- user agent (browser's default style sheet)
- user (browser's options)
- author (CSS provided by the page)

By default, this is the order in which different sources are processed, such that author's rules will override those of user and user agent.

THere is the `!important` declaration. This declaration is to balance the relative priority of user and author style sheets.

If user rule has `!important` applied to it, it will override even an author rule that also has `!important` applied to it.

The ascending order of importance:
1. User agent declarations
2. User declarations
3. Author declarations
4. Author `!important` declarations
5. User `!important` declarations

The flexibility is key because it allows users to override styles.

### Specificity
Every CSS rule has a particular weight:
- More or less important than others
- Deteremines which properties will be applied to the target element when there are conflicting rules
- If one rule is more specific than antoher, it overrides it
- If two rules share the same weight, source and specificity, the later one is applied.

### Calculating specificity
The quickest way is to add 1 for each element and pseudo-element, add 10 for each attribute, for example,  `[type="text"]`, class and pseudo-class (for example, `:link` or `:hover`); add 100 for each ID and add 1000 for inline style.

Examples:
- `**p.note**` 1 class + 1 element = 11
- `**sidebar p[lang="en"]**` 1 ID + 1 attr + 1 element = 100 + 10 + 1
- `**body #main .post ul li:last-child**` 1 ID + 1 class + 1 pseudo-class + 3 elements
= 100 + 10 + 1 + 3 = 123

A simpler method, is to start with a=0, b=0, c=0 and d=0:
- a=1 if the style is inline
- b=the number of IDs
- c=the number of attribute selectors, classes and pseudo-classes
- d=the number of element names and pseudo-elements

Examples:
- `**<p style="color:#000000;">**` a=1, b=0, c=0, d=0 -> 1000
- `footer nav li:last-child` a=0, b=0, c=1, d=3 -> 0013
- `#sidebar input:not([type="submit"])` a=0, b=1, c=1, d=1 -> 0111 ( the negation pseudo-class doesn't count)

If an imported style sheet (@import) is used, you have to declare them before all other rules. They would be considered as coming before all the other rules in CSS.

Finally, if two selectors turn out to have same specificity, the last one will override the previous one.

### Making specificity work
- When starting work on CSS, use generic selectors
- add specificity as you go along
- avoid using unnecessarily complicated selectors
- rely more on specificity, so that your style sheets are easier to edit and maintain

### Inheritance
- A way of propagating property values from parent elements to their children.
- For example the `font` property in the `body` tag will will inherited by other child elements, such as headings and paragraphs.

### How inheritance works
An element inherits the computed value from its parent.

Result of four-step calculation:
- Determined through specification ("specific value")
- Resolved into a value that is used for inheritance ("computed value")
- Converted into an absolute value if necessary ("used value")
- Transformed according to the limitations of the local environment ("actual value")

Specified value
- The user agent deteremines whether the value of the property comes from a style sheet is inherited

Computed value
- The specified value is resolved to a computed value and exists when a property doesn't apply. The doc doesn't have to be laid out

Used value
- Takes the computed value and resolves any dependencies (such as percentages)

Actual value
- Value used for final rendering
- Such as converting a decimal to an integer

CSS property specification - defines its initial value, the elements it applies to and inheritance status and computed value

For example, the `background-color` states:
- Name: background color
- Value: <color>
- Initial: transparent
- Applies to: all elements
- Inherited: no
- Percentages: N/A
- Media: visual
- Computed value: the computed colors

When an element inherits a value from its parent, it inherits its computed value.

### Using Inheritance
Imagine you had to specify the `font-size` or `font-family` instead of simpy adding it to the `body` element.

IE supports the `inherit` value only from version 8, except for `direction` and `visibility` properties.