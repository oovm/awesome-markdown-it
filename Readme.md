<!-- TOC -->

- [Grammar enhancement](#grammar-enhancement)
  - [markdown-it-container](#markdown-it-container)
  - [markdown-it-custom-block](#markdown-it-custom-block)
  - [markdown-it-sup](#markdown-it-sup)
  - [markdown-it-sub](#markdown-it-sub)
  - [markdown-it-ins](#markdown-it-ins)
  - [markdown-it-mark](#markdown-it-mark)
  - [markdown-it-deflist](#markdown-it-deflist)
  - [markdown-it-abbr](#markdown-it-abbr)
  - [markdown-it-katex](#markdown-it-katex)
  - [markdown-it-mathpix](#markdown-it-mathpix)
  - [markdown-it-highlight-lines](#markdown-it-highlight-lines)
  - [markdown-it-task-checkbox](#markdown-it-task-checkbox)
  - [markdown-it-anchor](#markdown-it-anchor)
  - [markdown-it-toc-and-anchor](#markdown-it-toc-and-anchor)
  - [markdown-it-header-sections](#markdown-it-header-sections)
  - [markdown-it-meta](#markdown-it-meta)
  - [markdown-it-front-matter](#markdown-it-front-matter)
  - [markdown-it-include](#markdown-it-include)
  - [markdown-it-replace-link](#markdown-it-replace-link)
- [Style and target and editors](#style-and-target-and-editors)
  - [markdown-it-terminal](#markdown-it-terminal)
  - [markdown-it-editor](#markdown-it-editor)
- [Plugin development](#plugin-development)
  - [markdown-it-loader](#markdown-it-loader)
  - [markdown-it-regexp](#markdown-it-regexp)
- [Use in other languages and frameworks](#use-in-other-languages-and-frameworks)
  - [markdown-it-vue](#markdown-it-vue)
  - [markdown-it-py](#markdown-it-py)

<!-- /TOC -->


## Grammar enhancement

### markdown-it-container

https://github.com/markdown-it/markdown-it-container

With this plugin you can create block containers like:

```
::: warning
*here be dragons*
:::
```

.... and specify how they should be rendered. If no renderer defined, `<div>` with
container name class will be created:

```html
<div class="warning">
<em>here be dragons</em>
</div>
```

Markup is the same as for [fenced code blocks](http://spec.commonmark.org/0.18/#fenced-code-blocks).
Difference is, that marker use another character and content is rendered as markdown markup.

### markdown-it-custom-block

https://github.com/posva/markdown-it-custom-block


Handle custom blocks transformations

```
@[example](hello)

@[video](video.mp4)
```

becomes

```
<example-hello/>
<video controls>
  <source src="video.mp4" type="video/mp4">
</video>
```


### markdown-it-sup

https://github.com/markdown-it/markdown-it-sup

> Superscript (`<sup>`) tag plugin for markdown-it markdown parser.


`29^th^` => `29<sup>th</sup>`


### markdown-it-sub

https://github.com/markdown-it/markdown-it-sub

> Subscript (`<sub>`) tag plugin for markdown-it markdown parser.

`H~2~0` => `H<sub>2</sub>O`

Markup is based on [pandoc](http://johnmacfarlane.net/pandoc/README.html#superscripts-and-subscripts) definition. But nested markup is currently not supported.

### markdown-it-ins

https://github.com/markdown-it/markdown-it-ins


> `<ins>` tag plugin for [markdown-it](https://github.com/markdown-it/markdown-it) markdown parser.

`++inserted++` => `<ins>inserted</ins>`

Markup uses the same conditions as CommonMark [emphasis](http://spec.commonmark.org/0.15/#emphasis-and-strong-emphasis).

### markdown-it-mark

https://github.com/markdown-it/markdown-it-mark

> `<mark>` tag plugin for [markdown-it](https://github.com/markdown-it/markdown-it) markdown parser.

`==marked==` => `<mark>inserted</mark>`

Markup uses the same conditions as CommonMark [emphasis](http://spec.commonmark.org/0.15/#emphasis-and-strong-emphasis).


### markdown-it-deflist

https://github.com/markdown-it/markdown-it-deflist

### markdown-it-abbr

https://github.com/markdown-it/markdown-it-abbr

> Abbreviation (`<abbr>`) tag plugin for [markdown-it](https://github.com/markdown-it/markdown-it) markdown parser.

Markup is based on [php markdown extra](https://michelf.ca/projects/php-markdown/extra/#abbr) definition, but without multiline support.

Markdown:

```
*[HTML]: Hyper Text Markup Language
*[W3C]:  World Wide Web Consortium
The HTML specification
is maintained by the W3C.
```

HTML:

```html
<p>The <abbr title="Hyper Text Markup Language">HTML</abbr> specification
is maintained by the <abbr title="World Wide Web Consortium">W3C</abbr>.</p>
```

### markdown-it-katex

https://github.com/waylonflinn/markdown-it-katex

### markdown-it-mathpix

https://github.com/Mathpix/mathpix-markdown-it

### markdown-it-highlight-lines


https://github.com/egoist/markdown-it-highlight-lines


### markdown-it-task-checkbox

https://github.com/linsir/markdown-it-task-checkbox


### markdown-it-anchor

https://github.com/valeriangalliat/markdown-it-anchor

### markdown-it-toc-and-anchor

https://github.com/medfreeman/markdown-it-toc-and-anchor

### markdown-it-header-sections

https://github.com/arve0/markdown-it-header-sections

### markdown-it-meta

https://github.com/CaliStyle/markdown-it-meta

### markdown-it-front-matter

https://github.com/parksb/markdown-it-front-matter

### markdown-it-include

https://github.com/camelaissani/markdown-it-include

### markdown-it-replace-link

https://github.com/martinheidegger/markdown-it-replace-link

## Style and target and editors

### markdown-it-terminal

https://github.com/trabus/markdown-it-terminal

### markdown-it-editor

https://github.com/k55k32/markdown-it-editor


## Plugin development



### markdown-it-loader

Webpack

https://github.com/unindented/markdown-it-loader


### markdown-it-regexp
https://github.com/rlidwka/markdown-it-regexp


## Use in other languages and frameworks

### markdown-it-vue

Vue

https://github.com/ravenq/markdown-it-vue

### markdown-it-py

Python

https://github.com/executablebooks/markdown-it-py
