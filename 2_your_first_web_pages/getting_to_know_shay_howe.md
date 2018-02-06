## Semantics Overview
Semantics is the practice of giving content meaning & structure.

Semantic code describes the value of content on a page. Several benefits:
- enabling computers
- screen readers
- search engines

Semantic HTML is easier to manage and work with.

## Divisions & Spans
`<div>`s and `<span>`s act as containers - solely for styling.

Block-level elements begin on a new line, stacking on top of one another, occupies available width.

We'll see block-level elements used for larger pieces such as paragraphs.

Inline-level elements fall into normal flow, and maintain the width of their content.
Inline level elements may be nested inside one another however cannot wrap block-level elements.

`<div>` - block-level element used to identify large groupings of content.
`<span>` - inline-level element used to identify smaller groupings of text.

```html
<!-- Division -->
<div class="social">
  <p>I may be found on...</p>
  <p>Additionally, I have a profile on...</p>
</div>

<!-- Span -->
<p>Soon we'll be <span class="tooltip">writing HTML</span> with the best of them.</p>
```
## Using Text-Based elements
### Headings
- Block-level elements, come in six different rankings, `<h1>` through `<h6>`.
- Headings quickly break up content and establish hierarchy, help search engines to index and determine content.

### Paragraphs
Paragraphs can appear one after the other, adding info to page.

### Bold Text with Strong
The `<strong>` inline-level element makes text bold and place importance on it.
The `<b>` means to stylistically offset text.

### Italicize Text with emphasis
The `<em>` inline-level element is used to place stressed emphasis.
`<i>` is used to convey text in an alternative voice or tone, almost as if placed in quotations.

## Building structure
`<header>, <nav>, <article>, <section>, <aside> and <footer>`

### Header
`<header>` element is used to identify top of a page.
Header may include heading, introductory text and even navigation.

`<header>` outlines the heading of a segment. Falls within the `<body>` element.

`<head>` is not displayed. Used to outline metadata. Falls directy in the `<html>` element.

### Navigation
`<nav>` identifies a section of major navigational links on a page.
Should be reserved for primary navigation sections only:
- global navigation
- table of contents
- previous/next links

Misc one-off links should use the anchor element.

### Article
Used to identify a section of self contained content.
Often use `<article>` to mark up blog posts, newspaper articles.

### Section
used to identify thematic group of content, generally includes a heading.

## Deciding between <article>, <section> or <div>
If content is being grouped solely for the styling purposes, doesn't provide value, use the `<div>` element.

If content adds to the document, can be independently redistributed, use `<article>` element. Helps outline a document.

If content represents a thematic group, use the `<section>` element. Helps outline a document.

### Aside
Holds sidebars, inserts or brief explanations, peripherally related to the content surrounding it.

### Footer
Identifies the closing or end of a page. Found at the bottom of its parent.
