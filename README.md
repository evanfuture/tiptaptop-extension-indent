# @tiptaptop/extension-indent

Hi! This is an extension for [tiptap](https://github.com/ueberdosis/tiptap). It adds an indentation command and lets you indent/outdent certain elements.

By default, `paragraph` and `listItem` types can have indentation applied. The way the are applied is simple, it just adds a `data-indent` property to the element in question. The styling is up to you, but here is a SCSS snippet that I've found useful:

```scss
@for $i from 1 through 8 {
  [data-indent='#{$i}'] {
    $val: $i * 3rem;
    padding-left: $val;
  }
}
```

--

## Usage

I'm primarily sharing this repo to get some help, but I will eventually publish an installable version on npm. Until then, you can just copy and paste the indent.ts file into your own project, and import it wherever you use a tiptap editor. For example:

```ts
import { Indent } from '...path...to/indent';
...
const editor  = new Editor({
      extensions: [
          Underline,
          Indent.configure({
              types: ['listItem', 'paragraph'],
              minLevel: 0,
              maxLevel: 8,
          }),
      ],
});
```
