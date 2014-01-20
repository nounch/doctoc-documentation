---
layout: documentation
title: "doctoc Tag"
permalink: /
---

# `doctoc` Tag

The `doctoc` tag renders a nested list of links to pages.

```
{% raw %}{% doctoc %}{% endraw %}
```

Here is some example output:

```html
<li><a href="/doc/About">About</a>
</li><li><a href="/doc/Documentation">Documentation</a>
  <ul>
    <li><a href="/doc/Documentation/doctoc_Tag">doctoc_Tag</a>
    </li>
  </ul>
</li><li><a href="/doc/Getting_started">Getting_started</a>
</li><li><a href="/doc/Overview">Overview</a>
</li>
```

The lists are nested according to the [W3C recommendation](http://www.w3schools.com/tags/tryit.asp?filename=tryhtml_lists2) where `li` elements are contained within other `li` elements.

The tree contains links to all nodes and all leafes in the tree. If some nodes do not specify a `index.html`/`index.markdown`/`index.md`/`index.textile` file, DocToc will automatically generate fallback index files instead.

## Conventions

The tree is exclusively generated from the hierarchical file structure in the top level directory of the Jekyll project. DocToc will render a page for every `index.{html,markdown,md,textile}` file anywhere in the tree. Every leaf node, however, has to have **its own directory with the name of the leaf which contains a `index.html`/`index.markdown`/`index.md`/`index.textile` file.**. This may seem counterintuitive, but is due to the way Jekyll sweeps up files for Markup to HTML conversion. The advantage is that every leaf can have multiple files which co-exist in one directory where unused files are given names without an HTML/Markdown/Textile extension.

Wrong:

```
Colors
  Bright_Colors
    red.markdown
    orange.markdown
    yellow.markdown
  Dark_Colors
    blue.markdown
    brown.markdown
```

Right:

```
Colors
  Bright_Colors
    red
      index.markdown
    orange
      index.markdown
    yellow
      index.markdown
  Dark_Colors
    blue
      index.markdown
    brown
      index.markdown
```

Any **non-leaf directory**, however, can contain an `index.html`/`index.markdown`/`index.md`/`index.textile` file which will be rendered as a page when the according node link in the TOC is clicked.

Any **underscore** in a directory name will be rendered as a single space in the HTML output.

**Any characters** allowed by the file system and recognized by Ruby are theoretically possible, but it makes sense to follow sane file/directory naming conventions and to move any uncommon character combinations down into the textual content of the file.

## Highlighting

DocToc can highlight the name of the current page in the TOC by applying the `doctoc-highlight` class to the corresponding `a` element.

```
{% raw %}{% doctoc highlight-current-node %}{% endraw %}
```

This class can then be used to style the link with CSS or to manipulate it using JavaScript.

Example output:

```html
<li><a href="/doc/About">About</a>
</li><li><a href="/doc/Documentation">Documentation</a>
  <ul>
    <li><a class="doctoc-highlight" href="/doc/Documentation/doctoc_Tag">doctoc_Tag</a>
    </li>
  </ul>
</li><li><a href="/doc/Getting_started">Getting_started</a>
</li><li><a href="/doc/Overview">Overview</a>
</li>
```
  

## Highlighting with a custom class

`doctoc` tag also takes an optional second argument along with `highlight-current-node` which represents the name of the class to be used instead of `doctoc-highlight`. Note: **No quotes** for the class name.

```
{% raw %}{% doctoc highlight-current-node, my-custom-class %}{% endraw %}
```

Example output:

```html
<li><a href="/doc/About">About</a>
</li><li><a href="/doc/Documentation">Documentation</a>
  <ul>
    <li><a class="my-custom-class" href="/doc/Documentation/doctoc_Tag">doctoc_Tag</a>
    </li>
  </ul>
</li><li><a href="/doc/Getting_started">Getting_started</a>
</li><li><a href="/doc/Overview">Overview</a>
</li>
```

## `parent-node` argument

`doctoc` takes the `parent-node` argument which renders the entire subtree for the current page if there is a subtree. The optional second argument specifies replacement text which is rendered if the current page does not have a subtree because it is a leaf node. The replacement text can be valid HTML and will be rendered as such.
