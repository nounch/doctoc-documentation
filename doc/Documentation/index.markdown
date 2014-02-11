---
layout: documentation
title: "Documentation"
permalink: /
---

# General Notes

Here are some general facts that one should be aware of.

## Text Arguments

Some Tags have optional text arguments which will become part of the rendered HTML. Except otherwise noted, those text snippedt can contain valid HTML tags which will be rendered as such.

## Top-Level Directory

DocToc has the requirement that the file hierarchy is placed in one top-level directory which is located in the root of the Jekyll project.

## Each Page File Lives In Its Own Directory
Each page file which represents a leaf node in the TOC tree has to be placed in its own directory. The name of the directory will make up the name of the leaf node rendered in the TOC tree, children/sibling lists, subtrees, parent links etc. The file has to have one of the following names:
  
- index.html
- index.markdown
- index.md
- index.textile

... where the file extension will determine the markup converter Jekyll is going to use (usual Jekyll behaviour).

## Node And Page Names

The names of nodes and pages are determined by their associated file and directory names. So the restrictions of the file system in use will be the restrictions of characters usable with links. However, it makes sense to restrict oneself to the usual set of alphanumeric characters since it is the whole point of DocToc to have an easily managable file tree instead of manually maintaining nested HTML lists or similar.

This is the only exception: Every underscore (`_`) will be converted to a single space in rendered links.

If file or directory names contain valid HTML markup, this markup will be rendered as HTML and will not be escaped in the final page. Avoid doing this.
