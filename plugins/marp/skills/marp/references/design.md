# Marp Design Guide

Effective slide design balances visual appeal with clear communication.

## Theme Selection

| Theme | Style | Best For | Example |
|-------|-------|----------|---------|
| `default` | Clean, minimal | Technical content, code-heavy slides | `examples/default-theme.md` |
| `gaia` | Gradient headers, modern | Keynotes, conference talks | `examples/gaia-theme.md` |
| `uncover` | Progressive reveals | Teaching, tutorials | `examples/uncover-theme.md` |

## Layout Patterns

### Title Slides

Use `lead` class for impactful title slides:

```markdown
<!-- _class: lead -->

# Presentation Title

**Your Name**
Your Organization
Date
```

### Section Dividers

Create clear section breaks with consistent styling:

```markdown
<!-- _class: lead -->

## Part One: Introduction
```

### Two-Column Layouts

Use flexbox for side-by-side content:

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

### Side-by-Side Image + Text

```markdown
<div style="display: flex; align-items: center; gap: 40px;">

![width:400px](image.png)

<div>

## Description

Explain the image with supporting text.

</div>

</div>
```

### Hero Images

Full-bleed background with overlay text:

```markdown
![bg fit:cover](hero-image.jpg)

<!-- _class: lead -->
<!-- _color: white -->

# Text Over Image
```

### Three Columns

```markdown
<div style="display: flex; gap: 30px; text-align: center;">

<div>

### Step 1

**Plan**

Define requirements
and scope.

</div>

<div>

### Step 2

**Build**

Implement the
solution.

</div>

<div>

### Step 3

**Deploy**

Ship to production.

</div>

</div>
```

### Comparison Boxes

```markdown
<div style="display: flex; gap: 40px;">

<div style="flex: 1; background: var(--marp-theme-bg); padding: 20px; border-radius: 8px;">

## Option A

- Feature 1
- Feature 2
- $10/month

</div>

<div style="flex: 1; background: var(--marp-theme-bg); padding: 20px; border-radius: 8px;">

## Option B

- Feature 1
- Feature 2
- Feature 3
- $15/month

</div>

</div>
```

### Code + Explanation

```markdown
<div style="display: flex; gap: 40px; align-items: center;">

<div>

\`\`\`javascript
const sum = (a, b) => a + b;
\`\`\`

</div>

<div>

## Arrow Function

Concise syntax for
simple function expressions.

**Perfect for:**
- Callbacks
- Array methods

</div>

</div>
```

### Stats + Details

```markdown
<div style="display: flex; align-items: center; gap: 60px;">

<div style="font-size: 80px; font-weight: bold; color: var(--marp-theme-accent);">

95%

</div>

<div>

## Customer Satisfaction

Our latest survey shows
overwhelming positive feedback.

*Survey of 1,000 users*

</div>

</div>
```

### Quote Layout

```markdown
<div style="display: flex; align-items: center; gap: 40px;">

<div>

![width:200px](avatar.jpg)

</div>

<div style="font-style: italic; font-size: 24px;">

"The best presentation I've
seen this year."

**— Jane Doe, CTO**

</div>

</div>
```

### Timeline

```markdown
<div style="display: flex; gap: 20px;">

<div style="text-align: center; flex: 1;">

### Q1

Planning phase

</div>

<div style="text-align: center; flex: 1;">

### Q2

Development

</div>

<div style="text-align: center; flex: 1;">

### Q3

Testing

</div>

<div style="text-align: center; flex: 1;">

### Q4

Launch

</div>

</div>
```

## Typography Best Practices

- **Titles**: 2-3 words per line max
- **Body**: 24-30px for readability
- **Code**: Large enough to read (use `fit` modifier for long lines)

### Content Density

Keep slides focused:

```markdown
✅ Good:
- Short, punchy bullets
- 3-5 points per slide
- One main idea per slide

❌ Bad:
- Long, rambling paragraphs
- Too much text that overwhelms the audience
- Multiple competing ideas
```

## Color Design

### Invert for Contrast

Use `invert` class to make key slides stand out:

```markdown
<!-- _class: invert -->

# Important Point

Stands out from surrounding slides.
```

### Theme Colors

Use CSS variables for consistent emphasis:

```markdown
<span style="color: var(--marp-theme-accent)">Key insight</span>
```

## Consistency Patterns

### Repeated Section Headers

```markdown
<!-- _class: lead -->

## Part One: Introduction

---

<!-- _class: lead -->

## Part Two: Implementation

---

<!-- _class: lead -->

## Part Three: Conclusion
```

### Image Placement

Choose one pattern and stick with it:
- Always left-align images
- Always center images
- Alternate sides for rhythm