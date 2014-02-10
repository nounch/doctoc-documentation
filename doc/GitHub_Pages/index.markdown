---
layout: documentation
title:  "GitHub Pages"
permalink: /
---

# Using DocToc With GitHub Pages

Using DocToc with GitHub pages is straightforward. Since GitHub Pages does not allow to run Jekyll plugins (to prevent arbitrary code execution), DocToc cannot be run live on GitHub Pages. Its output, however, can be hosted, however. After all, Jekyll is a static site generator.

Create an orphaned `gh-pages` branches in your project:

``` bash
git checkout --orphan gh-pages
```

Build the static site:

``` bash
jekyll build
```

Remove all Jekyll-related cruft, except `_site`:

``` bash
rm assets
rm css
rm _plugins
# Not: `rm _site'!
```

Warning: Do not remove git-specific files/directories (`.git`, `.gitignore` etc.)!

Move everything from `_site` to the top level directory, remove `_site` afterwards:

``` bash
mv _site/* .
rm _site
```

Push your branch:

``` bash
git push origin gh-pages
```
