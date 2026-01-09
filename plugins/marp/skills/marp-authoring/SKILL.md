---
name: Marp Authoring
description: Use when working with Marp presentations—creating, editing, or modifying .md files for Marp. Provides syntax reference, formatting patterns, directives, frontmatter options, slide separation, images, code blocks, speaker notes, and Marp-specific Markdown. Triggers: "marp", "create a presentation", "build slides", "work with marp", "marp file", "marp presentation", "marp syntax", "marp directives", "marp frontmatter", "marp markdown", "edit slides", "presentation.md"
---

# Marp Authoring Guide

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

For complete syntax details, see the reference files:

- **`references/syntax.md`** - Slide separation, directives, images, fragments, speaker notes, code blocks, math
- **`references/frontmatter.md`** - All frontmatter options (theme, paginate, style, etc.)
