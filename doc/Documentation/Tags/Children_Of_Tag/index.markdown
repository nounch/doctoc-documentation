---
layout: documentation
title: "doctoc_children_of Tag"
permalink: /
---

# `doctoc_children_of` Tag

`doctoc_children_of` renders a list of links to all direct children of the page with the specified path.

```
{% raw %}{% doctoc_children_of /doc/Documentation/ %}{% endraw %}
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
{% raw %}{% doctoc_children_of /doc/path/to/page/file/, Child Pages %}{% endraw %}
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

Leading and trailing slashes can be provided, but do not have to be provided. It does not matter if there is a leading and no trailing one or no trailing, but a leading one or none or both. DocToc will figure it out.

---------------------------------------------------------------------------

{% doctoc_children_of /doc/, <p>Live example (children of <code>/doc/</code>):</p> %}

---------------------------------------------------------------------------

It is the responsibility of the user to provide valid pathes.
