<!-- TOC -->

- [Grammar enhancement](#grammar-enhancement)
  - [markdown-it-container](#markdown-it-container)
  - [markdown-it-custom-block](#markdown-it-custom-block)
  - [markdown-it-sup](#markdown-it-sup)
  - [markdown-it-sub](#markdown-it-sub)
  - [markdown-it-ins](#markdown-it-ins)
  - [markdown-it-mark](#markdown-it-mark)
  - [markdown-it-abbr](#markdown-it-abbr)
  - [markdown-it-attrs](#markdown-it-attrs)
  - [markdown-it-deflist](#markdown-it-deflist)
  - [markdown-it-hashtag](#markdown-it-hashtag)
  - [markdown-it-math](#markdown-it-math)
  - [markdown-it-mathjax](#markdown-it-mathjax)
  - [markdown-it-katex](#markdown-it-katex)
  - [markdown-it-mathpix](#markdown-it-mathpix)
  - [markdown-it-texmath](#markdown-it-texmath)
  - [markdown-it-latex](#markdown-it-latex)
  - [markdown-it-latex2img](#markdown-it-latex2img)
  - [markdown-it-highlightjs](#markdown-it-highlightjs)
  - [markdown-it-prism](#markdown-it-prism)
  - [markdown-it-highlight-lines](#markdown-it-highlight-lines)
  - [markdown-it-implicit-figures](#markdown-it-implicit-figures)
  - [markdown-it-mermaid](#markdown-it-mermaid)
  - [markdown-it-multimd-table](#markdown-it-multimd-table)
  - [markdown-it-plantuml](#markdown-it-plantuml)
  - [markdown-it-checkbox](#markdown-it-checkbox)
  - [markdown-it-task-checkbox](#markdown-it-task-checkbox)
  - [markdown-it-task-lists](#markdown-it-task-lists)
  - [markdown-it-anchor](#markdown-it-anchor)
  - [markdown-it-toc-and-anchor](#markdown-it-toc-and-anchor)
  - [markdown-it-headinganchor](#markdown-it-headinganchor)
  - [markdown-it-header-sections](#markdown-it-header-sections)
  - [markdown-it-meta](#markdown-it-meta)
  - [markdown-it-front-matter](#markdown-it-front-matter)
  - [markdown-it-footnote](#markdown-it-footnote)
  - [markdown-it-include](#markdown-it-include)
  - [markdown-it-replace-link](#markdown-it-replace-link)
  - [markdown-it-emoji](#markdown-it-emoji)
- [editors and editor plugins](#editors-and-editor-plugins)
  - [markdown-it-editor](#markdown-it-editor)
- [Plugin development](#plugin-development)
  - [markdown-it-loader](#markdown-it-loader)
  - [markdown-it-regexp](#markdown-it-regexp)
  - [markdown-it-testgen](#markdown-it-testgen)
  - [markdown-it-for-inline](#markdown-it-for-inline)
- [Uncategorized](#uncategorized)
  - [markdown-it-terminal](#markdown-it-terminal)
  - [markdown-it-classy](#markdown-it-classy)
  - [markdown-it-cjk-breaks](#markdown-it-cjk-breaks)
  - [markdown-it-sanitizer](#markdown-it-sanitizer)
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

### markdown-it-attrs

https://github.com/arve0/markdown-it-attrs

Add classes, identifiers and attributes to your markdown with `{.class #identifier attr=value attr2="spaced value"}` curly brackets, similar to [pandoc's header attributes](http://pandoc.org/README.html#extension-header_attributes).

Example input:
```md
# header {.style-me}
paragraph {data-toggle=modal}
```

Output:
```html
<h1 class="style-me">header</h1>
<p data-toggle="modal">paragraph</p>
```

Works with inline elements too:
```md
paragraph *style me*{.red} more text
```

Output:
```html
<p>paragraph <em class="red">style me</em> more text</p>
```

And fenced code blocks:
<pre><code>
```python {data=asdf}
nums = [x for x in range(10)]
```
</code></pre>

Output:
```html
<pre><code data="asdf" class="language-python">
nums = [x for x in range(10)]
</code></pre>
```

You can use `..` as a short-hand for `css-module=`:

```md
Use the css-module green on this paragraph. {..green}
```

Output:
```html
<p css-module="green">Use the css-module green on this paragraph.</p>
```

Also works with spans, in combination with the [markdown-it-bracketed-spans](https://github.com/mb21/markdown-it-bracketed-spans) plugin (to be installed and loaded as such then):

```md
paragraph with [a style me span]{.red}
```

Output:
```html
<p>paragraph with <span class="red">a style me span</span></p>
```

### markdown-it-deflist

https://github.com/markdown-it/markdown-it-deflist

### markdown-it-hashtag

https://github.com/svbergerem/markdown-it-hashtag

> hashtag (`#tag`) plugin for [markdown-it](https://github.com/markdown-it/markdown-it) markdown parser.

`#hashtag` => `<a href="/tags/hashtag" class="tag">#hashtag</a>`


### markdown-it-math

https://github.com/runarberg/markdown-it-math

### markdown-it-mathjax

https://github.com/classeur/markdown-it-mathjax

### markdown-it-katex

https://github.com/waylonflinn/markdown-it-katex

### markdown-it-mathpix

https://github.com/Mathpix/mathpix-markdown-it

### markdown-it-texmath

https://github.com/goessner/markdown-it-texmath


### markdown-it-latex

https://github.com/tylingsoft/markdown-it-latex

### markdown-it-latex2img

https://github.com/MakerGYT/markdown-it-latex2img

### markdown-it-highlightjs

https://github.com/valeriangalliat/markdown-it-highlightjs

### markdown-it-prism

https://github.com/jGleitz/markdown-it-prism

### markdown-it-highlight-lines


https://github.com/egoist/markdown-it-highlight-lines


### markdown-it-implicit-figures

https://github.com/arve0/markdown-it-implicit-figures

### markdown-it-mermaid

https://github.com/tylingsoft/markdown-it-mermaid

### markdown-it-multimd-table

https://github.com/RedBug312/markdown-it-multimd-table

### markdown-it-plantuml

https://github.com/gmunguia/markdown-it-plantuml

### markdown-it-checkbox

https://github.com/mcecot/markdown-it-checkbox

### markdown-it-task-checkbox

https://github.com/linsir/markdown-it-task-checkbox

### markdown-it-task-lists

https://github.com/revin/markdown-it-task-lists


### markdown-it-anchor

https://github.com/valeriangalliat/markdown-it-anchor

### markdown-it-toc-and-anchor

https://github.com/medfreeman/markdown-it-toc-and-anchor

### markdown-it-headinganchor

https://github.com/adam-p/markdown-it-headinganchor

### markdown-it-header-sections

https://github.com/arve0/markdown-it-header-sections

### markdown-it-meta

https://github.com/CaliStyle/markdown-it-meta

### markdown-it-front-matter

https://github.com/parksb/markdown-it-front-matter

### markdown-it-footnote

https://github.com/markdown-it/markdown-it-footnote


> Footnotes plugin for [markdown-it](https://github.com/markdown-it/markdown-it) markdown parser.

Markup is based on [pandoc](http://johnmacfarlane.net/pandoc/README.html#footnotes) definition.

__Normal footnote__:

```
Here is a footnote reference,[^1] and another.[^longnote]

[^1]: Here is the footnote.

[^longnote]: Here's one with multiple blocks.

    Subsequent paragraphs are indented to show that they
belong to the previous footnote.
```

html:

```html
<p>Here is a footnote reference,<sup class="footnote-ref"><a href="#fn1" id="fnref1">[1]</a></sup> and another.<sup class="footnote-ref"><a href="#fn2" id="fnref2">[2]</a></sup></p>
<p>This paragraph won’t be part of the note, because it
isn’t indented.</p>
<hr class="footnotes-sep">
<section class="footnotes">
<ol class="footnotes-list">
<li id="fn1"  class="footnote-item"><p>Here is the footnote. <a href="#fnref1" class="footnote-backref">↩</a></p>
</li>
<li id="fn2"  class="footnote-item"><p>Here’s one with multiple blocks.</p>
<p>Subsequent paragraphs are indented to show that they
belong to the previous footnote. <a href="#fnref2" class="footnote-backref">↩</a></p>
</li>
</ol>
</section>
```

__Inline footnote__:

```
Here is an inline note.^[Inlines notes are easier to write, since
you don't have to pick an identifier and move down to type the
note.]
```

html:

```html
<p>Here is an inline note.<sup class="footnote-ref"><a href="#fn1" id="fnref1">[1]</a></sup></p>
<hr class="footnotes-sep">
<section class="footnotes">
<ol class="footnotes-list">
<li id="fn1"  class="footnote-item"><p>Inlines notes are easier to write, since
you don’t have to pick an identifier and move down to type the
note. <a href="#fnref1" class="footnote-backref">↩</a></p>
</li>
</ol>
</section>
```

### markdown-it-include

https://github.com/camelaissani/markdown-it-include

### markdown-it-replace-link

https://github.com/martinheidegger/markdown-it-replace-link

### markdown-it-emoji

https://github.com/markdown-it/markdown-it-emoji

## editors and editor plugins

### markdown-it-editor

https://github.com/k55k32/markdown-it-editor


## Plugin development



### markdown-it-loader

Webpack

https://github.com/unindented/markdown-it-loader


### markdown-it-regexp
https://github.com/rlidwka/markdown-it-regexp

### markdown-it-testgen

https://github.com/markdown-it/markdown-it-testgen

### markdown-it-for-inline

https://github.com/markdown-it/markdown-it-for-inline

## Uncategorized

### markdown-it-terminal

https://github.com/trabus/markdown-it-terminal


### markdown-it-classy

https://github.com/andrey-p/markdown-it-classy

### markdown-it-cjk-breaks

https://github.com/markdown-it/markdown-it-cjk-breaks

### markdown-it-sanitizer

https://github.com/svbergerem/markdown-it-sanitizer

## Use in other languages and frameworks

### markdown-it-vue

Vue

https://github.com/ravenq/markdown-it-vue

### markdown-it-py

Python

https://github.com/executablebooks/markdown-it-py
