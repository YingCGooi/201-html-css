## Semantically Identifying Figures & Captions
`<figure>` and `<figcaption>` were created to semantically mark up self-contained content or media.

### Figure

`<figure>` block-level element is used to:
- identify and wrap self-contained content
- may surround images, audio clips, videos, blocks of code, diagrams, illustrations
- if moved from main portion of a page to another location. It should not disrupt the content or legibility.

```html
<figure>
  <img src="dog.jpq" alt="A black, brown, and white dog wearing a kerchief">
</figure>
```

### Figure Caption
To add caption or legend, the `<figcaption>` is used.
It may appear at the top of, bottom of or anywhere within `<figure>`

```html
<figure>
  <img src="dog.jpg">
  <figcaption>A beautiful black, brown, and white hound dog wearing kerchief.</figcaption>
</figure>
```
