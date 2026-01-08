# Marp Plugin for Claude Code

A Claude Code plugin for creating and exporting slide decks using [Marp](https://marp.app/) — the Markdown presentation ecosystem.

## Features

- **Create presentations** with minimal templates using `/marp-create`
- **Export to multiple formats** — PDF, HTML, PowerPoint (PPTX), and images
- **Smart format inference** — Claude detects the output format you need
- **Design guidance** — Built-in skills for Marp syntax and presentation design
- **Theme examples** — Ready-to-use presentation templates

## Prerequisites

Install Marp CLI globally:

```bash
npm install -g @marp-team/marp-cli
```

Verify installation:

```bash
marp --version
```

## Commands

### `/marp-create` [filename]

Create a new Marp presentation with a minimal template.

```bash
/marp-create my-talk.md
```

The template includes:
- YAML frontmatter with `marp: true`
- Title slide using the `lead` class
- One example content slide

### `/marp-export` [input-file]

Export a Markdown presentation to slides. The output format is inferred from context or you'll be prompted.

```bash
# Export to PDF
/marp-export deck.md

# Claude will infer PDF from context
```

Supported formats:
- **PDF** — Best for sharing and printing
- **HTML** — Interactive presentations in browser
- **PPTX** — Editable in PowerPoint/Keynote
- **PNG/JPEG** — Individual slide images

## Skills

### Marp Authoring

Triggers when you ask about:
- "How do I write Marp?"
- "Marp syntax"
- "Marp frontmatter"
- "Marp directives"

Covers:
- YAML frontmatter options
- Slide separation with `---`
- Directives for slide control
- Images, code blocks, tables
- Speaker notes and transitions

### Marp Design

Triggers when you ask about:
- "Marp themes"
- "Slide layout"
- "Presentation design"
- "Marp images"

Covers:
- Built-in themes (default, gaia, uncover)
- Layout patterns (title slides, two-column)
- Visual hierarchy and typography
- Image handling and positioning
- Design best practices

## Example Presentation

```markdown
---
marp: true
theme: gaia
paginate: true
title: My Presentation
---

<!-- _class: lead -->

# My Presentation

**Author Name** • Date

---

# Agenda

- First topic
- Second topic
- Third topic

---

## Code Example

```javascript
function hello() {
  console.log("Hello Marp!");
}
```
```

## Quick Reference

| Need | Command |
|------|---------|
| New presentation | `/marp-create filename.md` |
| Export to slides | `/marp-export filename.md` |
| Learn syntax | Ask about "Marp syntax" |
| Design help | Ask about "Marp themes" |

## Plugin Structure

```
marp/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   ├── marp-create.md
│   └── marp-export.md
├── skills/
│   ├── marp-authoring/
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── syntax.md
│   │       └── frontmatter.md
│   └── marp-design/
│       ├── SKILL.md
│       └── examples/
│           ├── default-theme.md
│           ├── gaia-theme.md
│           ├── two-column.md
│           └── uncover-theme.md
└── README.md
```

## Links

- [Marp Official Site](https://marp.app/)
- [Marp CLI Repository](https://github.com/marp-team/marp-cli)
- [Marp Documentation](https://marp.app/docs)

## License

MIT
