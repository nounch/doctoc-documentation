---
layout: documentation
title: "doctoc_subtree_of Tag"
permalink: /
---

# `doctoc_children_of` Tag

`doctoc_subtree_of` renders a list of links to all pages in the subtree of the page with the specified path.

```
{% raw %}{% doctoc_subtree_of /doc/Documentation/ %}{% endraw %}
```

The rendered HTML is a nested list of `a` elements.

This tag takes an optional argument text which will be prepended to the rendered `ul` element as is; e.g. if the argument is a valid HTML element it will be rendered as such.

```
{% raw %}{% doctoc_subtree_of /doc/path/to/page/file/, Child Pages %}{% endraw %}
```

Leading and trailing slashes can be provided, but do not have to be provided. It does not matter if there is a leading and no trailing one or no trailing, but a leading one or none or both. DocToc will figure it out.

---------------------------------------------------------------------------

{% doctoc_subtree_of /doc/, <p>Live example (subtree of <code>/doc/</code>):</p> %}

---------------------------------------------------------------------------

It is the responsibility of the user to provide valid pathes.

Note: `doctoc_subtree_of` does not provide highlighting of the current page.
