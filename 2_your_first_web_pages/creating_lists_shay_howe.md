### Unordered Lists
- List of related items where order does not matter.
- Accomplied using block-level element `<ul>`
- The default solid dot that precede each `<li>` is called the list item marker, can be changed using CSS

### Ordered Lists
The order in which items are presented is important.
Typically rendered as a numbered list.

#### type
Indicates the numbering type:
- 'a' lowercase
- 'A' uppercase
- 'i' indicates lowercase Roman numerals
- 'I' uppercase Roman numberals
- '1' numbers

#### Start Attribute
- Defines the number from which an ordered list should start.
- Identify exactly which number an ordered list should begin counting from
- accepts only integer values

```HTML
<ol start="30">
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>  
</ol>
```
### Reversed Attribute
When used in `<ol>` elenent, allows a list to appear in reverse order.
The reversed attribute is a boolean attribute.

### Value Attribute
May be used on an individual `<li>` element within an ordered list to change its value.
The number of any list item appearing below a list item will be calculated accordingly.

```HTML
<ol>
  <li>Head north on N Halsted St</li>
  <li value="9">Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li><!-- continue from 10. -->
</ol>
```
