---
layout: documentation
title:  "Configuration"
permalink: /
---

# Configuration

## Sorting

The sorting order of elements in the TOC, in sibling/parent lists, subtrees and `parent-node` subtrees can be achieved using the `doctoc_sort` tag which can read custom sorting rules from `_config/sorting.yml`. More on this can be found on the [sort tag page](/doc/Documentation/Tags/Sort_Tag).

## Page Root Directory

By default, the root directory for pages is called `pages`. However, a custom name can be used if this is explicitely specified in `_config.yml` in the root directory of the project:

```
doctoc_dir: /doc
```

Do not worry about leading or trailing slashes. DocToc will figure it out.


## Fallback File Extension

The extension for the fallback file that will be generated automatically, if there is none yet, can be specified setting the `doctoc_fallback_extension` property in `_config.yml` in the Jekyll project root directory.

```
doctoc_fallback_extension: markdown
```

The default content of this file is HTML, so any converter will render it correctly. The only reason to set the extension is if you are not using pretty URLs (though you should!) and want to specify a custom extension instead of `html`.

The default value is: `html`
