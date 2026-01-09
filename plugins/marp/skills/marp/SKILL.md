---
name: Marp
description: Use when working with Marp presentations—creating, editing, or modifying .md files for Marp. Covers syntax (directives, slide separation, images, fragments), frontmatter options, and design principles (layout patterns, visual hierarchy, content density, typography). Triggers: "marp", "create a presentation", "build slides", "work with marp", "marp file", "marp presentation", "marp syntax", "marp directives", "marp frontmatter", "make slides look good", "improve design", "layout help"
---

# Marp Guide

Marp uses **CommonMark + GitHub Flavored Markdown (GFM)** for standard formatting, plus Marp-specific extensions for slides.

> **Need to learn basic Markdown?** See [Markdown Guide](https://www.markdownguide.org/)

---

## Quick Start

A minimal Marp presentation:

```markdown
---
marp: true
theme: gaia
---

# Slide 1

Content here.

---

# Slide 2

More content.
```

## Marp-Specific Essentials

| Feature | Syntax |
|---------|--------|
| **Enable Marp** | `marp: true` in frontmatter |
| **Separate slides** | `---` (also `___`, `***`, `- - -`) |
| **Title slide** | `<!-- _class: lead -->` |
| **Background image** | `![bg](image.jpg)` |
| **Image sizing** | `![width:300px](img.jpg)` |
| **Speaker notes** | `<!-- Note: text -->` |
| **Incremental reveal** | `<!-- _pause -->` |

---

## Reference Files

### Syntax & Configuration
- **`references/syntax.md`** - Slide separation, directives, images, fragments, speaker notes, code blocks, math
- **`references/frontmatter.md`** - All frontmatter options (theme, paginate, style, etc.)

### Design Guidance
- **`references/design.md`** - Layout patterns, visual hierarchy, typography, content density, theme selection

### Examples
- **`examples/`** - Complete presentation templates:
  - `default-theme.md` - Clean, technical presentation
  - `gaia-theme.md` - Modern keynote style
  - `two-column.md` - Advanced layout techniques
  - `uncover-theme.md` - Progressive reveal pattern