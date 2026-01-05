# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site for the Harambee Cultural Society (harambee.ca), a Canadian charitable organization supporting children of African heritage. The site uses the Blowfish theme installed as a git submodule.

## Common Commands

```bash
# Development server with live reload
hugo server

# Development server including draft content
hugo server -D

# Build static site (outputs to /public)
hugo

# Build with minification for production
hugo --minify
```

## Architecture

### Directory Structure

- `config/_default/` - Hugo configuration split across multiple TOML files:
  - `hugo.toml` - Core site settings (baseURL, taxonomies, outputs)
  - `params.toml` - Theme parameters (layout options, features, appearance)
  - `menus.en.toml` - Navigation menus (main header menu, footer links)
  - `languages.en.toml` - Language-specific settings (title, logo, copyright)
  - `markup.toml` - Markdown rendering settings (KaTeX math support enabled)

- `content/` - Site content in Markdown with TOML frontmatter
  - `_index.md` - Homepage content
  - `posts/` - Announcements/blog posts (configured as mainSections)
  - Individual pages: `about.md`, `donate.md`, `summerfestival.md`

- `layouts/shortcodes/` - Custom Hugo shortcodes
  - `hero-pane.html` - Custom styled hero section component using Tailwind CSS

- `assets/` - Site assets processed by Hugo Pipes
  - `css/compiled/` - Compiled CSS
  - `img/` - Images including logo

- `themes/blowfish/` - Git submodule containing the Blowfish theme

### Theme Configuration

The site uses homepage layout "page" with recent posts shown. Key params.toml settings:
- `colorScheme = "blowfish"`
- `defaultAppearance = "light"` with auto-switching enabled
- Search enabled, code copy disabled
- Article settings: shows date, author, reading time, word count

### Content Patterns

Content files use TOML frontmatter (`+++`). Example frontmatter params:
- `showAuthor = false` - Hide author on specific pages
- `layout = "simple"` - Use simplified layout variant

## Theme Documentation

Blowfish theme docs: https://blowfish.page/docs/
