# Marp Frontmatter Options

Complete reference for YAML frontmatter options in Marp presentations.

## Required Fields

### marp

Must be set to `true` to enable Marp processing:

```yaml
---
marp: true
---
```

## Basic Metadata

### title

Presentation title:

```yaml
---
title: My Amazing Presentation
---
```

### description

Presentation description:

```yaml
---
description: A comprehensive guide to Marp
---
```

### author

Author name:

```yaml
---
author: Jane Doe
---
```

### date

Presentation date:

```yaml
---
date: 2025-01-08
---
```

## Theme Options

### theme

Select built-in theme:

```yaml
---
theme: default   # or: gaia, uncover
---
```

Available themes:
- `default` - Clean, minimal design
- `gaia` - Distinctive gradient headers
- `uncover` - Progressive slide reveals

### themeSet

Path to custom theme CSS file:

```yaml
---
themeSet: ./themes/custom.css
---
```

Multiple theme paths:

```yaml
---
themeSet:
  - ./themes/theme1.css
  - ./themes/theme2.css
---
```

## Pagination

### paginate

Enable slide numbers:

```yaml
---
paginate: true
---
```

## Transition Settings

### transition

Set slide transition effect (for HTML output with bespoke template):

```yaml
---
transition: fade
---
```

Transitions: `fade`, `slide`, `convex`, `concave`, `zoom`

## HTML Options

### html

Enable HTML in markdown:

```yaml
---
html: true
---
```

### allowLocalFiles

Allow loading local files in HTML output:

```yaml
---
allowLocalFiles: true
---
```

## Style Injection

### style

Add custom CSS to the presentation:

```yaml
---
style: |
  section {
    font-family: 'Arial', sans-serif;
    background-color: #f0f0f0;
  }
  h1 {
    color: #3498db;
  }
---
```

## Slide Configuration

### size

Set slide dimensions:

```yaml
---
size: 16:9
---
```

Common sizes: `4:3`, `16:9`, `16:10`

## PDF Options (CLI)

These are typically set via CLI flags, but can be pre-configured:

```yaml
---
# In CLI use: --pdf-notes
# In CLI use: --pdf-outlines
---
```

## Complete Example

```yaml
---
marp: true
theme: gaia
paginate: true
title: Introduction to Marp
description: Learn how to create beautiful slide decks with Markdown
author: Jane Developer
date: 2025-01-08
transition: slide
style: |
  section {
    font-family: 'Helvetica Neue', Arial, sans-serif;
  }
  h1 {
    color: #2c3e50;
  }
---
```

## Advanced: Custom Engines

### engine

Specify a custom Marpit-based engine:

```yaml
---
engine: ./custom-engine.js
---
```

## Global Options via CLI

Some options are set via CLI flags rather than frontmatter:

| CLI Flag | Purpose |
|----------|---------|
| `--pdf` | Export as PDF |
| `--html` | Export as HTML |
| `--pptx` | Export as PowerPoint |
| `--images png` | Export as PNG images |
| `--pdf-notes` | Include speaker notes in PDF |
| `--pdf-outlines` | Add PDF bookmarks |
| `--allow-local-files` | Allow local file access |
| `--theme <name>` | Override theme |
| `--template <name>` | HTML template (bespoke) |
| `--browser <name>` | Browser for conversion |
