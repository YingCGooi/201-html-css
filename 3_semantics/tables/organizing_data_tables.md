Tables were used for positioning content as well as for building overall layout of a page. However, with CSS, tables are styled to make information more legible.

### Creating a Table
#### Table
Use the `<table>` element to initialize a table on a page. Signifies this element will be tabular data displayed in columns and rows.

#### Table Row
May be added using `<tr>` element
The number of table rows may be substantial.

#### Table Data
Once a table is defined, rows within have been set up, data cells may be added to the table.
Listing multiple `<td>` elements one after other will create columns.

```html
<table>
  <tr>
    <td>Don&#8217;t Make Me Think by Steve Krug</td>
    <td>In Stock</td>
  </tr>

  <tr>
    <td>Bulletproof Web Design by Dan Cederholm</td>
    <td>In Stock</td>
    <td>1</td>
    <td>$30.17</td>
  </tr>
</table>
```
#### Table Header
The table header `<th>` should be used to designate a heading for column or rows of cells.

The importance of using `<th>` over `<td>` is that table header provides semantic value (data within the cell is a heading.)

The `scope` attribute helps to identify what content a table header relates to, whether or not the values `col, row, colgroup, and rowgroup`
The most commonly used are `col` and `row`.

Using the `<th>` element, along with `scope` tremendously helps screen readers make sense of a table.

```html
<table>
  <tr>
    <th scope="col">Item</th>
    <th scope="col">Availability</th>
    <th scope="col">Qty</th>
    <th scope="col">Price</th>
  </tr>

  <tr>
    <td>Bulletproof Web Design by Dan Cederholm</td>
    <td>In Stock</td>
    <td>1</td>
    <td>$30.17</td>
  </tr>
</table>
```
#### The Headers Attribute
Similar to `scope` attribute.
`scope` attribute may only be used on the `<th>` element.

The value of `headers` attribute on a `<td>` or `<th>` element needs to match `id` attribute value of `<th>` element.

#### Table Caption
Provides a caption or title for a table.
Will help users identify what the table pertains to.
`<caption>` element must come immediately after the opening `<table>` tag.

#### Table Head, Body and Foot
The content within tables can be broken up into groups, including head, body and foot.
`<thead>`, `<tbody>` and `<tfoot>` help to structurally organize tables.

`<thead>` wraps the heading row. The table head should be placed at the top of a table.
After any `<caption>` and before any `<tbody>` element.

The `<tbody>` should contain the primary data within a table, while `<tfoot>` contains data that outlines the contents of a table.

```html
<table>
  <caption>Design and Front-End Development Books</caption>
  <thead>
    <tr>
      <th scope="col">Item</th>
      <th scope="col">Availability</th>
      <th scope="col">Qty</th>
      <th scope="col">Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>...</td>
      <td>...</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td></td>
      <td></td>
    </tr>
  </tfoot>
</table>
```

#### Combining Multiple Cells
Two or more cells need to be combined.
We can use the `colspan` and `rowspan` attributes.
The two attributes wok on either the `<td>` or `<th>` elements.

```html
<thead>
  <tr>
    <th scope="col" colspan="2">Item</th>
    <th scope="col">Qty</th>
    <th scope="col">Price</th>
  </tr>
</thead>
```

### Table Borders
#### Border Collapse Property
Table consists of parent `<table>` element as well as nested `<th>` or `<td>` elements.
The border of one element sitting next to that of another element.

The `border-collapse` property determines a table's border model.
3 valid values:
- collapse
- separate
- inherit

```css
table {
  border-collapse: collapse;
}

th,
td {
  border: 1px solid #cecfd5;
  padding: 10px 15px;
}
```

#### Border Spacing Property
`border-spacing` property can determine how much space appears between the borders. Only works when `border-collapse` property value is separate.

The declaration for `border-spacing: 5px 10px`

```css
table {
  border-collapse: separate;
  border-spacing: 4px;
}
```

#### Adding Borders to Rows
Borders cannot be applied to `<tr>` elements or table structural elements.
So when we want to put a border between rows, thought is required.

```css
table {
  border-collapse: collapse;
}

th, td {
  border-bottom: 1px solid #cecfd5;
  padding: 10px 15px;
}

tfoot tr:last-child td {
  border-bottom: 0;
}
```

### Table Striping
"Striping" table rows with alternating background colors makes the rows clearer and provides a visual cue for scanning info.

An easier way is to use the `nth-child` pseudo-class selector with an `even` or `odd` argument.

```css
tbody tr:nth-child(even) {
  background: #f0f0f2;
}

td:first-child {
  border-left: 1px solid #cecfd5;
}
```

#### Aligning Text
To align text vertically, use `vertical-align` - works only with inline and table-cell elements.

`vertical-align` accepts handful of different values. The most popular values are `top, middle, bottom`

These values vertically position text.

We can clean up the layout of our table of books.
