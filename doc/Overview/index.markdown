---
layout: documentation
title:  "Overview"
permalink: /
---

# Overview

DocToc does three things.

First, it parses the list of all pathes to pages provided by the Jekyll plugin API.

Example:

```
/doc/Renderer/List_Component/Sorted_List
/doc/Renderer/List_Component/Unsorted_List
/doc/Renderer/List_Component/Ordered_List
/doc/Renderer/Navigation_Component/Button
/doc/Renderer/Navigation_Component/Link
# ...
```

... then it puts the directories and files in a hierarchical tree structure

```
doc
  Renderer
    List Component
      Sorted list
      Unsorted list
      Ordered list
    Navigation_Component
      Button
      Link
# ...
```

... and finally provides Liquid tags which render HTML (the TOC-like nested list of links to individual pages) and allow sorting of elements in the tree.

Like this:

```
{% raw %}
{% doctoc %}
{% endraw %}
```

... which renders the TOC tree.

Or this:

```
{% raw %}
{% doctoc_breadcrumb %}
{% endraw %}
```

... which inserts a breadcrumb with an arrow as separator.

Or this one:

```
{% raw %}
{% doctoc_sort custom, reverse %}
{% endraw %}
```

... which does not render anything, but reads _config/sorting.yml and applies the sorting rules specified there.
