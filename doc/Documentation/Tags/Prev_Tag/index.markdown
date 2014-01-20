---
layout: documentation
title: "doctoc_prev Tag"
permalink: /
---

# `doctoc_prev` Tag

The `doctoc_prev` tag provides a link to the previous page in the TOC tree. The previous page is determined by performing a right-most tree traversal; e.g. if one styles the TOC tree in the usual top-down nested HTML list manner, the previous page is the link in the row below the current one, no matter how wide it is indented.

The tag takes a required argument which determines the exact text of the rendered link.

```
{% raw %}{% doctoc_prev only_name %}{% endraw %}
# => "Node name"

{% raw %}{% doctoc_prev prev_with_parens %}{% endraw %}
# => "Previous (Node name)"

{% raw %}{% doctoc_prev only_prev %}{% endraw %}
# => "Previous"

{% raw %}{% doctoc_prev only_prev_small_caps %}{% endraw %}
# => "previous"

{% raw %}{% doctoc_prev custom, ← Previous %}{% endraw %}
# => "← Previous"
```

If the first element in the "list" is reached, the previous link will point to the last element in the "list".
