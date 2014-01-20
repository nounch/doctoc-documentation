---
layout: documentation
title: "doctoc_sort Tag"
permalink: /
---

# `doctoc_sort` Tag

This tag causes the TOC tree to be sorted before rendering. Sorting happens on every individual level of the hierarchy e.g. every hierarchy level will be treated as a flat list and sorted according to the criteria specified. By default, the tree is sorted **lexically**.

If a different sorting order order should be applied, `doctoc_sort` offers three sorting criteria.

## Lexical Sorting

```
{% raw %}{% doctoc_sort lexical %}{% endraw %}
```

## Sorting By String Length

```
{% raw %}{% doctoc_sort string_length %}{% endraw %}
```

## Custom Sorting:

```
{% raw %}{% doctoc_sort custom %}{% endraw %}
```

The `custom` argument forces DocToc to read the `_config/sorting.yml` file in the root of the pages directory and to apply its rules. If this config file does not exist yet, it will be created automatically and populated with sample configuration.

The default content of `_config/sorting.yml` looks like this:


```yaml
---
#==========================================================================
# Each key refers to an indentation level; e.g. `1' is the top level, `2'
# is the second indentation level, `3' the third one etc.
#==========================================================================

# Top level
1:
  - colors
  - animals

# Second level of indentation
2:
  - dark
  - bright

  - more nonsense
  - nonsense

# Third level of indentation
3:
  - orange
  - yellow
  - red

  - CDE Truck
  - ABC Truck

  - blue
  - purple

#==========================================================================
# The `all' section includes a sorting order which should be applied
# throughout all indentation levels.
#==========================================================================
all:
  - FGH Truck
  - IJK Truck
```

## Reversing The Sort Order

Every one of the three  sorting criteria takes an optional second argument `reverse`. If this is present, every list on every level of the hierarchy will be sorted first and reversed afterwards.

```
{% raw %}{% doctoc_sort lexical, reverse %}{% endraw %}
{% raw %}{% doctoc_sort string_length, reverse %}{% endraw %}
{% raw %}{% doctoc_sort custom, reverse %}{% endraw %}
```
