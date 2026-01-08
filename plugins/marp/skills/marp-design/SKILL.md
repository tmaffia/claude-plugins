---
name: Marp Design
description: Use when user asks about Marp themes, slide layouts, visual design, presentation styling, or design best practices. Covers built-in themes (default, gaia, uncover), layout patterns (two-column, title slides), visual hierarchy, typography, images, color design, and content density. Triggers: "marp themes", "slide layout", "marp design", "presentation design", "marp images", "make slides look good"
---

# Marp Design Guide

Effective slide design balances visual appeal with clear communication. Marp's themes and layout tools help create professional presentations from Markdown.

See `examples/` for complete presentation examples using different themes and design patterns.

## Built-in Themes

Marp includes three themes with distinct personalities:

| Theme | Style | Best For |
|-------|-------|----------|
| `default` | Clean, minimal | Technical content, code-heavy slides |
| `gaia` | Gradient headers, modern | Keynotes, conference talks |
| `uncover` | Progressive reveals | Teaching, tutorials |

Set theme in frontmatter:

```yaml
---
marp: true
theme: gaia
---
```

## Slide Layout Patterns

### Title Slides

Use the `lead` class for impactful title slides:

```markdown
<!-- _class: lead -->

# Presentation Title

**Your Name**
Your Organization
Date
```

### Section Dividers

Create clear section breaks:

```markdown
<!-- _class: lead -->

# Part Two

## Advanced Topics
```

### Two-Column Layouts

Use inline styles for columns:

```markdown
<div style="display: flex; gap: 40px;">

<div>

## Left Column

- Point one
- Point two

</div>

<div>

## Right Column

- Point three
- Point four

</div>

</div>
```

## Visual Hierarchy

### Font Sizing

Use heading levels for hierarchy:

```markdown
# Main Heading (largest)

## Secondary Heading

### Tertiary Heading

Regular body text for content.
```

### Emphasis

Draw attention strategically:

```markdown
Key point: **Critical information**

Important: *Important concept*

Reference: `code or technical terms`
```

## Images

### High-Impact Hero Images

Full-bleed background images:

```markdown
![bg fit:cover](hero-image.jpg)

<!-- _class: lead -->
<!-- _color: white -->

# Text Over Image
```

### Side-by-Side Content

Image with text:

```markdown
<div style="display: flex; align-items: center; gap: 40px;">

![width:400px](image.png)

<div>

## Description

Explain the image
with supporting text.

</div>

</div>
```

## Color Design

### Theme Colors

Each theme has a color palette. Use inline styles to emphasize:

```markdown
<span style="color: var(--marp-theme-accent)">Highlighted text</span>
```

### Invert for Contrast

Use `invert` class for dark/light contrast:

```markdown
<!-- _class: invert -->

# High contrast slide

Stands out from surrounding slides.
```

## Typography Best Practices

### Font Sizing

- **Titles**: 2-3 words per line max
- **Body**: 24-30px for readability
- **Code**: Large enough to read (use `fit` for long lines)

### Line Length

Keep text concise:

```markdown
✅ Good:
- Short, punchy bullets
- 3-5 points per slide

❌ Bad:
- Long, rambling paragraphs that are hard to read
- Too much text that overwhelms the audience
```

## Content Density

### Less is More

```markdown
# Effective Slide

- One main idea
- Supporting bullets
- One impactful image

# Overloaded Slide

- Too many points
- Dense text blocks
- Multiple competing images
- Audience can't focus
```

## Progressive Disclosure

Use `uncover` theme or pause directive:

```markdown
- First point
- Second point

<!-- _pause -->

- Third point (reveals on click)
```

## Code Presentation

### Readable Code

```markdown
\`\`\`javascript { .line-numbers }
// Brief comments only
function example() {
  return "clear code";
}
\`\`\`
```

Use `fit` class for long lines:

```markdown
\`\`\`javascript
const reallyLongVariableName = someFunctionThatReturnsARatherLongStringValue();
\`\`\`
```

## Consistency

### Repeated Patterns

Use consistent section headers:

```markdown
<!-- _class: lead -->

## Part One: Introduction

---

<!-- _class: lead -->

## Part Two: Implementation
```

### Consistent Image Placement

Choose a pattern and stick with it:
- Always left-aligned images
- Or always center images
- Or alternating sides

## Examples

See `examples/` for complete presentations:

- `examples/default-theme.md` - Clean, technical presentation
- `examples/gaia-theme.md` - Modern keynote style
- `examples/two-column.md` - Advanced layout techniques
- `examples/uncover-theme.md` - Progressive reveal pattern
