---
layout: documentation
title: "doctoc_breadcrumb Tag"
permalink: /
---

# `doctoc_breadcrumb` Tag

The breadcrumb tag renders a breadcrumb to the current page with clickable links for all parent nodes. There are two different render modi:

# Quick And Easy Rendering

```
{% raw %}{% doctoc_breadcrumb %}{% endraw %}
```

This will render consecutive links (`a` tags) which are not grouped together or wrapped in a `ul`. This is handy if you do not want to spend too much time styling just to make it look like a breadcrumb. This mode takes an optional second argument which will be used as the separator between the links. If no second argument is given, the default separator `/` will be used.

```
{% raw %}{% doctoc_breadcrumb → %}{% endraw %}
```

Note: The leaf element of the breadcrumb  is always a plain `span` element and not a clickable link since it always represents the current page.

# Nitpicky Rendering

This mode takes the constant value `nitpicky` as its first argument and will render a nested list of links. This is a more correct representation of a breadcrumb, but will require additional styling.

```
{% raw %}{% doctoc_breadcrumb nitpicky %}{% endraw %}
```

This mode also takes an optinal second argument which will be used as separator.

```
{% raw %}{% doctoc_breadcrumb nitpicky → %}{% endraw %}
```
