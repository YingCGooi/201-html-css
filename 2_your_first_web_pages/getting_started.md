HTML tells:
- your browser what kind of information each element represents
- provides semantic meaning for content


### The HTML element
```
<html>
```

The `<html>` tag informs the browser that a document contains HTML.

### Document Type Definition
Document type definition tells the browser what subset of HTML we are using, we can specify earlier versions of HTML as well, but it's important to tell the browser which one we're using.

It must be the first item in an HTML document. You can't have whitespace before the DTD.

```HTML
<!doctype html>
<html>
  Hello, Internet!
</html>
```

The `!` is part of the DTD and must be present.
It does not have a closing tag. DTD is NOT a tag nor an element.

### Title element
Displays this text in the title bar.
The browser does not display the title as part of the page.
The title is not 'content'.

### Body Element
```HTML
<!doctype html>
<html>
  <title>Welcome!</title>
  <body>
    Hello, Internet!
  </body>
</html>
```

Represents the entire page body.

### Meta Element
Contains data about the page (metadata) that the browser can use, not necessary to display the page.

```HTML
<meta />
```
We need to provide information with attributes.

### Attributes
The `<html>` tag lets us specify the main language

```HTML
<html lang="en-US">
```

Attributes provide information the browser may need:
- path of image
- default value of an input text field
- character set

rel = relation attribute, used to determine what kind of resource the link will fetch.
Example:
`<link rel="stylesheet"></link>`

### Paragraph Element
Any other whitespace and newlines are swallowed by the browser.

The `<p>` element wraps a single paragraph and displays in a separate area below the previous content. Also adds some vertical spacing above and below.

`<p>` is a container for paragraph.

### Heading Element
The `<h1>` represents a heading element.
You can think of a chapter that has a section and subsections, each with heading type.

Chapter titles uses the largest font, while subheadings use progressively smaller sizes.

HTML has six level of headings.

### Text Formatting Elements
**Elements**

- Strong: Text has higher importance than surrounding text, typically boldfaces it.
- em: Adds emphasis to the text, typically italicizes it. stress emphasis.
- b: Stylistically offset text, example: ES6 adds the keywords const and let. Do not apply this to text which has specific importance.
- i: alternate voice text. Ex: I said "Hello", She said "Goodbye". Technical terms, foreign language phrases, or fictional character thoughts.
- sub: lowers the vertical positioning of text and decreases size. Also known as superscript.
- sup: raises vertical positioning of text. Also called superscript

### Div and Span Elements
Don't use `h1`, `h2` for paragraphs, use `p` instead.
Don't use `<b>` and `<i>` for boldfaces and italics. Use `<strong>` and `<em>` instead.

Sometimes you need to treat some content as a unit, but no elements provide appropriate semantic meaning. Use the `div` or `span` element.
They don't supply any meaning, but they do provide a way to treat it as a unit.

Difference is that `div` elements are 'block' elements. While `span` elements are `inline` by default.

`div` is like a container for a block or content.
`span` is more like one of the text-formatting elements from previous section. They have no special styling.
