---
name: Marp Authoring
description: Use when user asks about Marp syntax, Markdown directives, frontmatter options, or how to write/create Marp presentations. Covers slide separation, directives (lead, invert, paginate), images, code blocks, speaker notes, and Marp-specific Markdown patterns. Triggers: "marp syntax", "how to write marp", "marp directives", "marp frontmatter", "marp markdown"
---

# Marp Authoring Guide

Marp uses Markdown with extended syntax for creating slide decks. Every Marp presentation starts with YAML frontmatter and uses specific directives for slide separation and formatting.

See `references/syntax.md` for complete syntax details and `references/frontmatter.md` for all frontmatter options.

## Frontmatter

Every Marp file must begin with YAML frontmatter containing `marp: true`:

```yaml
---
marp: true
theme: gaia
paginate: true
---
```

## Slide Separation

Use horizontal rules (`---`) to separate slides:

```markdown
# Slide 1

Content here.

---

# Slide 2

More content.
```

## Directives

Marp directives are HTML comments that control slide behavior:

- `<!-- _class: lead -->` - Create title/landing slide with large centered text
- `<!-- _paginate: false -->` - Hide slide numbers for this slide
- `<!-- _header: '' -->` - Clear header for this slide
- `<!-- _footer: '' -->` - Clear footer for this slide

```markdown
<!-- _class: lead -->

# Presentation Title

**Author Name**
```

## Slide Deck Directives

Global directives affect multiple slides:

```markdown
<!-- _class: lead -->

# Title Slide

---

<!-- _class: invert -->

# Dark Slide

---

<!-- _header: 'Section One' -->
<!-- _footer: 'Page 1' -->

# Regular Slide
```

## Markdown Patterns

### Lists

```markdown
- Regular bullet
- Another bullet

1. Numbered item
2. Another numbered item
```

### Images

```markdown
![alt text](image.jpg)

![width:300px](image.jpg)
![height:200px](image.jpg)
![fit](photo.png)

![bg](background.jpg)         # Background image
![bg fit](photo.png)          # Fitted background
![bg opacity:0.5](img.png)    # Semi-transparent bg
```

### Code Blocks

```markdown
\`\`\`javascript
function hello() {
  console.log("Hello Marp!");
}
\`\`\`
```

### Formatting

```markdown
**bold text**
*italic text*
~~strikethrough~~

`inline code`

[Link text](https://example.com)
```

### Tables

```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
```

## Speaker Notes

Add presenter notes (visible in PDF with `--pdf-notes`):

```markdown
Slide content.

<!-- Note: This is a speaker note that explains the slide in more detail. -->
```

## Split Slides

Split content across multiple slides automatically:

```markdown
<!-- _class: split -->

# Two Column Layout

Left column content.

---

Right column content.
```

For detailed syntax reference, see `references/syntax.md`. For all frontmatter options, see `references/frontmatter.md`.
