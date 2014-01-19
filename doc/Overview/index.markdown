---
layout: documentation
title:  "Overview"
permalink: /
---

# DocWhat?

DocToc is a navigation plugin for [Jekyll](http://jekyllrb.com/) that lets you put all your pages in a directory and automatically generates a hierarchical navigation (TOC) with links to all pages. It also gives you

- handy "Previous"/"Next" links,
- a list of links to all siblings of
  + the current
  + or any other tree node,
- a subtree for
  + the current
  + or any other tree node
- a link to the parent of the current node
- a breadcrumb for the current page

and it automatically generates index pages for nodes which do not have any "index.html", "index.markdown"/"index.md" or "index.textile" pages yet so no link will point to an non-existing page. All components are reasonably customizable and freely stylable.

This is a big deal since it frees you from having to organize your pages as either posts with proper date values in their names (Jekyll is a blog engine afterall) or as pages which are scattered across your top level directory. In other words: **It effectively makes Jekyll a documentation generator.** You simply organize your files in a directory hierarchy, provide a layout file and let DocToc do the rest. Your readers will be presented with an easy-to-navigate hierarchical site navigation and you have the power to point to entire subtrees, sibling or children lists of your documentation. Also, you do not have to care if you forgot to add a file somewhere in the directory structure, DocToc will add a fallback index file which can link to a parent page or any other part of your docs.
