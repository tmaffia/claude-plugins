---
name: marp-create
description: Create a new Marp presentation from a minimal template
argument-hint: [filename]
---

# Marp Presentation Creator

Create a new Marp presentation file with a minimal template.

## Arguments

- `filename` (optional): Name for the presentation file. If not provided, ask the user.

## Template Content

Create a minimal Marp presentation with:

1. **YAML frontmatter** with:
   - `marp: true`
   - `theme` (default: gaia)
   - `paginate` (for slide numbers)
   - `title` and `description` placeholders

2. **Example slides** (minimal):
   - Title slide using `<!-- _class: lead -->`
   - One content slide demonstrating basic syntax

## Example Template

```markdown
---
marp: true
theme: gaia
paginate: true
title: Your Presentation Title
description: A brief description
author: Your Name
---

<!-- _class: lead -->

# Your Presentation Title

**Your Name** • Date

---

# Section Title

- Bullet point
- Another point
- Sub-point with emphasis

![height:300px](https://via.placeholder.com/800x400)
```

## Implementation

1. If no filename provided, ask: "What would you like to name the presentation file?"
2. Validate filename has `.md` extension, add if missing
3. Check if file already exists, warn user before overwriting
4. Write the template content to the file
5. Confirm creation with file path and suggest next steps (e.g., "Run `/marp-export <filename>` to convert to slides")

## Prerequisites

Assume Marp CLI is installed. Do not provide installation instructions.
