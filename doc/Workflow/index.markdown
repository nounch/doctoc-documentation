---
layout: documentation
title:  "Workflow"
permalink: /
---

# Disabling TOC links

By default, nodes in the TOC tree are clickable links which point either to a predefined page or to the customizable fallback page, If certain nodes should not be clickable at all, i.e. if they are merely used as headlines, they can be styled accordingly, of course. This, however will not disable the link. To actually disable the link, consider using following CSS:

```css
pointer-event: none;
```

# Collapsable TOC Nodes

DocToc does not provide a way to label TOC nodes with classes other than the highlighting class (default: `doctoc-highlight`). If nodes should be collapsable, it is advised to use JavaScript instead. One possible scenario is this:

1. Insert an element (i.e. a triangle/arrow symbol) before each `a` element in the TOC tree.
2. Add an event listener to each newly insered element.
3. Provide a callback for the listender which will collapse/uncollapse the according child elements.

# Multiple Tags

For each tag that renders HTML there can be multiple instances per page. Example: multiple "Previous"/"Next" link pairs in different locations on the same page.
