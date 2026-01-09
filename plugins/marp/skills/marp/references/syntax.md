# Marp Syntax Reference

Marp-specific syntax and directives. Assumes knowledge of CommonMark/GFM Markdown.

## Slide Separation

Slides are separated by horizontal rules. Multiple separator styles are supported:

```markdown
# Slide 1

Content.

---

# Slide 2

---

# Slide 3 (using ___)

___

# Slide 4 (using ***)

***

# Slide 5 (using spaced dashes)
- - -
```

## Directives

Directives are HTML comments that control slide appearance and behavior.

### Slide Class Directive

```markdown
<!-- _class: lead -->
<!-- _class: invert -->
<!-- _class: lead + invert -->
```

| Class | Effect |
|-------|--------|
| `lead` | Large centered text, title slide style |
| `invert` | Inverted colors (light text on dark background) |

### Pagination Control

```markdown
<!-- _paginate: false -->
```

Hide slide numbers for specific slides.

### Header/Footer Override

```markdown
<!-- _header: '' -->
<!-- _footer: '' -->
<!-- _header: 'Conference 2025' -->
<!-- _footer: 'John Doe' -->
```

Clear or set custom header/footer per slide.

### Color Override

```markdown
<!-- _color: '#ff0000' -->
<!-- _backgroundColor: '#1a1a1a' -->
<!-- _backgroundGradient: 'linear-gradient(to right, #000428, #004e92)' -->
```

Set text color, background color, or gradient for a slide.

## Image Syntax (Marp Extensions)

### Sizing Modifiers

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
![bg](background.jpg)       # Stretch to fill
![bg fit](background.jpg)   # Fit with aspect ratio
![bg contain](background.jpg)   # Contain within slide
![bg cover](background.jpg)     # Cover slide
```

### Background Effects

```markdown
![bg opacity:0.3](overlay.png)       # Semi-transparent
![bg right:20% bottom:30%](logo.png) # Positioned
```

### Multiple Background Layers

```markdown
![bg](bg1.jpg)
![bg](bg2.png)
```

Stack multiple background images.

## Code Blocks

### Marp-Specific Options

```markdown
\`\`\`javascript { .line-numbers }
const x = 1;
\`\`\`
```

```markdown
\`\`\`javascript { .highlight-lines[2|4] }
const a = 1;
const b = 2; // highlighted
const c = 3;
const d = 4; // highlighted
\`\`\`
```

```markdown
\`\`\`javascript { .line-numbers .highlight-lines[2] }
const a = 1;
const b = 2; // highlighted
\`\`\`
```

Combine multiple modifiers by space-separating them.

## Math

Marp supports KaTeX for math typesetting:

```markdown
Inline: $E = mc^2$

Block:
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
```

## Speaker Notes

Only visible in presenter mode or PDF with `--pdf-notes`:

```markdown
# Slide Content

<!-- Note: This explains the slide content in more detail. -->
```

## Fragments (Incremental Display)

### Pause Directive

```markdown
- First point
- Second point

<!-- _pause -->

- Third point (appears after click)
```

### Continue Directive

Keep content on the same slide (no increment):

```markdown
- First point

<!-- _continue -->

- Second point (appears on same slide)

<!-- _continue -->

- Third point
```

### Fragmented Lists

Use special list markers for incremental reveals:

```markdown
* Appears first
* Appears second
* Appears third
```

```markdown
1) Appears first
2) Appears second
3) Appears third
```

The `*` bullet and `1)` numbered style create incremental reveals automatically.

## Slide Size

Custom dimensions via CSS in frontmatter style block:

```markdown
---
marp: true
style: |
  section {
    width: 1280px;
    height: 720px;
  }
---
```