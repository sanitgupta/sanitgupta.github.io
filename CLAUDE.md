# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal academic/portfolio website for Sanit Gupta, hosted on GitHub Pages. There is no build system, package manager, or framework — the entire site is a single `index.html` file with supporting assets.

## Structure

- `index.html` — the entire website; all content lives here
- `css/stylesheet.css` — custom styles; uses Lato (body) and Titillium Web (headings) loaded from Google Fonts
- `css/academicons.min.css` + `fonts/academicons.*` — icon font for academic icons
- `data/scramble.js` — Jeff Donahue's bubble-sort email obfuscation script, used to hide the email address from scrapers
- `data/` — images (PNG) and PDFs for projects/papers

## Developing

Open `index.html` directly in a browser — no server needed. To preview with a local server:

```sh
python3 -m http.server 8000
```

## Key conventions

- Custom HTML elements (`<heading>`, `<papertitle>`, `<name>`, `<wall>`, `<email>`) are styled via `stylesheet.css` — they are not standard HTML tags.
- The email address in the page is intentionally scrambled. The `scrambledString` constructor in `scramble.js` takes the scrambled string and an index permutation; updating the email requires recomputing the permutation.
- The `#news` list is fixed-height (`178px`) with `overflow-y: auto` to create a scrollable news section.
- Social/icon links use Font Awesome 4.x loaded from `https://use.fontawesome.com/9ed47fb20b.js` (a kit URL — do not change).
- The site layout uses nested `<table>` elements for structure (academic website convention from the Jon Barron template).
