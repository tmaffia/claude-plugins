# Marp Syntax Reference

Complete reference for Marp Markdown syntax and directives.

## Slide Separation

Slides are separated by horizontal rules (`---`):

```markdown
# Slide 1

Content.

---

# Slide 2

More content.

---

# Slide 3

Final slide.
```

## Directives

Directives are HTML comments that control slide appearance and behavior.

### Slide Class Directive

Apply predefined classes to slides:

```markdown
<!-- _class: lead -->

# Title Slide
```

Available classes:
- `lead` - Large centered text, title slide style
- `invert` - Inverted colors (light text on dark background)
- `invert + lead` - Combined classes

```markdown
<!-- _class: invert -->

# This slide has inverted colors
```

### Pagination Control

Control slide numbers per slide:

```markdown
<!-- _paginate: false -->

# This slide has no number
```

### Header/Footer Override

Override global header/footer for specific slides:

```markdown
<!-- _header: '' -->
<!-- _footer: '' -->

# Slide without header or footer
```

Set custom header/footer:

```markdown
<!-- _header: 'Conference 2025' -->
<!-- _footer: 'John Doe' -->

# Slide with custom header/footer
```

### Color Override

Set text color for a slide:

```markdown
<!-- _color: '#ff0000' -->

# Red text
```

### Background Override

Set slide background:

```markdown
<!-- _backgroundColor: '#1a1a1a' -->

# Slide with dark background
```

With gradient:

```markdown
<!-- _backgroundGradient: 'linear-gradient(to right, #000428, #004e92)' -->

# Gradient background
```

## Image Syntax

### Basic Images

```markdown
![Alt text](image.jpg)
```

### Sizing

```markdown
![width:300px](image.jpg)
![height:200px](image.jpg)
![width:80%](image.jpg)
```

### Fitting

```markdown
![fit](image.jpg)           # Fit within slide
![fit:cover](image.jpg)     # Cover entire slide
```

### Background Images

```markdown
![bg](background.jpg)           # Stretch to fill
![bg fit](background.jpg)       # Fit with aspect ratio
![bg contain](background.jpg)   # Contain within slide
![bg cover](background.jpg)     # Cover slide
```

### Background Opacity

```markdown
![bg opacity:0.3](overlay.png)  # Semi-transparent overlay
```

### Positioned Backgrounds

```markdown
![bg right:20% bottom:30%](logo.png)
```

### Multiple Background Layers

```markdown
![bg](bg1.jpg)
![bg](bg2.png)
```

## Code Blocks

### Basic Syntax Highlighting

```markdown
\`\`\`javascript
function hello() {
  console.log("Hello Marp!");
}
\`\`\`
```

### Line Numbers

```markdown
\`\`\`javascript { .line-numbers }
const x = 1;
\`\`\`
```

### Highlight Lines

```markdown
\`\`\`javascript { .highlight-lines[2|4] }
const a = 1;
const b = 2; // highlighted
const c = 3;
const d = 4; // highlighted
\`\`\`
```

### Inline Code

```markdown
Use `inline code` for emphasis.
```

## Lists

### Unordered Lists

```markdown
- Item 1
- Item 2
  - Nested item
  - Another nested
- Item 3
```

### Ordered Lists

```markdown
1. First item
2. Second item
3. Third item
```

### Task Lists

```markdown
- [x] Completed task
- [ ] Incomplete task
```

## Text Formatting

```markdown
**Bold text**
*Italic text*
~~Strikethrough~~
**_Bold and italic_**

`Inline code`

==Highlight== (requires theme support)
```

## Links

```markdown
[Link text](https://example.com)

[Relative link](./other-file.md)
```

## Tables

```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |
```

### Alignment

```markdown
| Left | Center | Right |
|:-----|:------:|------:|
| L    | C      | R     |
```

## Math

Marp supports KaTeX for math typesetting:

### Inline Math

```markdown
The equation $E = mc^2$ is famous.
```

### Block Math

```markdown
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
```

## Speaker Notes

Add presenter notes (only visible in presenter mode or PDF with notes):

```markdown
# Slide Content

<!-- Note: This is a speaker note that explains the slide content in more detail. It's useful for presenters but won't appear in the actual slides. -->
```

## Fragments (Incremental Display)

Show elements incrementally:

```markdown
- First point
- Second point
- Third point

<!-- _pause -->

- Fourth point (appears after click)
```

Or use the `<!-- _continue -->` directive to keep content on same slide:

```markdown
# Slide Title

- First point

<!-- _continue -->

- Second point (appears on same slide)

<!-- _continue -->

- Third point
```

## Slide Size

Set custom slide size in frontmatter:

```yaml
---
marp: true
style: |
  section {
    width: 1280px;
    height: 720px;
  }
---
```
