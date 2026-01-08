# Claude Code Plugins

A collection of plugins for [Claude Code](https://claude.ai/code).

## Adding the Marketplace

Add this repository as a marketplace in Claude Code:

```bash
claude plugin marketplace add https://github.com/tmaffia/claude-plugins
```

Then install the Marp plugin:

```bash
claude plugin install marp
```

## Available Plugins

### [Marp](./plugins/marp/)

Create and export slide decks using [Marp](https://marp.app/) — the Markdown presentation ecosystem.

**Features:**
- Create presentations with minimal templates
- Export to PDF, HTML, PowerPoint (PPTX), and images
- Smart format inference
- Design guidance and theme examples

**Usage:**
```bash
/marp-create my-talk.md    # Create new presentation
/marp-export deck.md       # Export to slides
```

## Contributing

Each plugin lives in its own subdirectory following the [Claude Code plugin structure](https://github.com/anthropics/claude-code/tree/main/docs/plugins).

## License

MIT 
