---
layout: documentation
title: "doctoc_next Tag"
permalink: /
---

# `doctoc_next` Tag

The `doctoc_next` tag provides a link to the next page in the TOC tree. The next page is determined by performing a right-most tree traversal; e.g. if one styles the TOC tree in the usual top-down nested HTML list manner, the next page is the link in the row below the current one, no matter how wide it is indented.

The tag takes a required argument which determines the exact text of the rendered link.

```
{% raw %}{% doctoc_next only_name %}{% endraw %}
# => "Node name"

{% raw %}{% doctoc_next next_with_parens %}{% endraw %}
# => "Next (Node name)"

{% raw %}{% doctoc_next only_next %}{% endraw %}
# => "Next"

{% raw %}{% doctoc_next only_next_small_caps %}{% endraw %}
# => "next"

{% raw %}{% doctoc_next custom, Next →%}{% endraw %}
# => "Next →"
```

If the last element in the "list" is reached, the next link will point to the first element in the "list".
