---
layout: documentation
title: "doctoc_sibling Tag"
permalink: /
---

# `doctoc_sibling` Tag

`doctoc_sibling` renders a list of links to all siblings of the current page excluding the current page itself.

```
{% raw %}{% doctoc_sibling %}{% endraw %}
```

Example output:

```html
<ul>
  <li>
    <a href="/doc/About">About</a>
  </li>
  <li>
    <a href="/doc/Getting started">Getting started</a>
  </li>
  <li>
    <a href="/doc/Overview">Overview</a>
  </li>
</ul>
```

This tag takes an optional argument text which will be prepended to the rendered `ul` element as is; e.g. if the argument is a valid HTML element it will be rendered as such.

```
{% raw %}{% doctoc_sibling <p>Sibling Pages</p> %}{% endraw %}
```

Example output:

```html
<p>Sibling Pages</p>
<ul>
  <li>
    <a href="/doc/About">About</a>
  </li>
  <li>
    <a href="/doc/Getting started">Getting started</a>
  </li>
  <li>
    <a href="/doc/Overview">Overview</a>
  </li>
</ul>
```
