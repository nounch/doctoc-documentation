---
layout: documentation
title: "doctoc_up Tag"
permalink: /
---

# `doctoc_up` Tag

The `doctoc_up` tag takes any text as argument and renders it as a link to the parent node. If no additionla text is provided, the name of the parent node itself will be used.

```
# Custom text
{% raw %}{% doctoc_up Go up %}{% endraw %}

# No text (defaults to node name)
{% raw %}{% doctoc_up %}{% endraw %}
```

The text supplied to `doctoc_up` as argument can in fact be valid HTML and will be rendered as such:

```
{% raw %}{% doctoc_up <p>Go up<p> %}{% endraw %}
```
