---
layout: documentation
title:  "Getting started"
permalink: /
---


# Getting started

## 1. A new project

Run the usual Jekyll initialization

```
jekyll new .
```

## 2. A new file hierarchy

Make a new hierarchy of pages in the root of your Jekyll project (where pages would usually live).

Example:

```
pages  # <-- For now, call this `pages'!
  API_v3
    index.markdown      # <-- `layout: documenataion'
    Retrieving_user_data
      Name
        index.markdown  # <-- `layout: documenataion'
      Age
        index.markdown  # <-- `layout: documenataion'
      Location
        index.markdown  # <-- `layout: documenataion'
    Posting_new_data
      index.markdown    # <-- `layout: documenataion'
      Comment
        index.markdown  # <-- `layout: documenataion'
      Status_update
        index.markdown  # <-- `layout: documenataion'
  API_v2
    index.markdown      # <-- `layout: documenataion'
# ...
```

## 3. A new layout file

Create a new `documentation.html` layout file in the `_layouts` directory and put this inside:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello DocToc</title>
    <meta charname="utf-8" />

  </head>
  
  <body>

    <h1>DocToc Demo</h1>

    {% raw %}{% doctoc_breadcrumb %}{% endraw %}

    {% raw %}{% doctoc %}{% endraw %}

    {% raw %}{{ content }}{% endraw %}

  </body>
</html>
```

Now make sure all the `index.markdown` files in your file hierarchy use the `documentation.html` layout by adding the `layout: documentation` to the front-matter part of each file.

Or just copy this:

```
---
layout: documentation
title:  "Dummy Title"
permalink: /
---

# Dummy Header

And some dummy text.
```

## 4. A new feeling

Fire up Jekyll...

```
jekyll server --watch --port 8002 --trace
```

... and navigate to `http://localhost:8002/pages/`

You should see a breadcrumb, a TOC tree and your content. Click around in the tree. Did you notice that even for nodes where you did not specify a `index.markdown` file DocToc did provide a fallback page with a link to its parent - if there is a parent node?
