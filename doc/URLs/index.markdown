---
layout: documentation
title:  "URLs"
permalink: /
---

# URLs

# Base URLs

DocToc does not emit leading slashes (`/`) for navigation links so they can be used in conjunction with a base URL. This allows for a custom slug prefix that makes sense for the target page (e.g. `/internal/v3/doc/Overview` where `/internal/v3/` is specified as the base URL).

### `_config.yml`

However, this means that a base URL *has* to be specify in `_config.yml`:

```yaml
baseurl: /internal/v3
```

### Layout File

This base URL can then be used in the template file (e.g. `_layouts/documentation.html`):

```html
<head>
  <!-- ... -->
  <base href="{{ site.baseurl }}/"/>
  <!-- ... -->
</head>
```

### Asset Links

Links to assets should also use the right base URL:

```html
<!-- ... -->
<link rel="stylesheet" href="{{ site.baseurl }}/css/main.css" type="text/css" media="screen" />
<link rel="stylesheet" href="{{ site.baseurl }}/css/404.css" type="text/css" media="screen" />
<!-- ... -->
```

### Different Base URL

If a different base URL should be (e.g. while running Jekyll locally), Jekyll's `--baseurl` flag can be used to override the config settings:

``` bash
jekyll serve --watch --port=8002 --trace --baseurl='/different/baseurl/'
```

If no base URL at all should be used, a simple slash (`/`) is sufficient:

``` bash
jekyll serve --watch --port=8002 --trace --baseurl='/'
```

# No Base URL At All

If there should not be any slug prefix, technically speaking the base URL is `/`. So both, a `baseurl` config entry and a `base` tag are still necessary.

`_config.yml`:

```yaml
baseurl: /
```

Layout file:


```html
<head>
  <!-- ... -->
  <base href="{{ site.baseurl }}/"/>
  <!-- ... -->
</head>
```

If this is not desirable, a web server may be instructed to serve the files regardless. It is not advisable, though, since, when deciding to prefix the URLs in the future, all asset links will have to be updated manually.


# GitHub Pages

When using project pages, GitHub Pages automatically prefixes slugs with the project name, e.g.:

```
http://username.github.io/project-name/
```

So simply adding a `baseurl` config with the project name will point all navigation and asset links to the right URL:

```yaml
baseurl: /project-name
```

Of course, the layout file should make use of this base URL:

```html
<head>
  <!-- ... -->
  <link rel="stylesheet" href="{{ site.baseurl }}/css/main.css" type="text/css" media="screen" />
  <link rel="stylesheet" href="{{ site.baseurl }}/css/404.css" type="text/css" media="screen" />
  <!-- ... -->
  <base href="{{ site.baseurl }}/"/>
  <!-- ... -->
</head>
```
