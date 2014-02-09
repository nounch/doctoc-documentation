---
layout: documentation
title: "doctoc_children Tag"
permalink: /
---

# `doctoc_children` Tag

`doctoc_children` renders a list of links to all direct children of the current page.

```
{% raw %}{% doctoc_children %}{% endraw %}
```

Example output:

```html
<ul>
  <li>
    <a href="/doc/Documentation/DocToc Breadcrumb Tag">DocToc Breadcrumb Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Children Tag">DocToc Children Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Sort Tag">DocToc Sort Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Tag">DocToc Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Up Tag">DocToc Up Tag</a>
  </li>
</ul>

```

This tag takes an optional argument text which will be prepended to the rendered `ul` element as is; e.g. if the argument is a valid HTML element it will be rendered as such.

```
{% raw %}{% doctoc_children Child Pages %}{% endraw %}
```

Example output:

```html
Child Pages
<ul>
  <li>
    <a href="/doc/Documentation/DocToc Breadcrumb Tag">DocToc Breadcrumb Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Children Tag">DocToc Children Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Sort Tag">DocToc Sort Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Tag">DocToc Tag</a>
  </li>
  <li>
    <a href="/doc/Documentation/DocToc Up Tag">DocToc Up Tag</a>
  </li>
</ul>

```


