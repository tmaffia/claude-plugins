---
name: marp-export
description: Export Markdown to slides using Marp (PDF, HTML, PPTX, images)
argument-hint: [input-file]
---

# Marp Exporter

Convert a Markdown presentation to slide decks using Marp CLI.

## Arguments

- `input-file` (optional): Path to the Markdown file to convert.

## Output Format Inference

Determine the output format from context:

1. **Explicit mentions**: User mentions "PDF", "HTML", "PowerPoint", "PPTX", "PNG", "images"
2. **File extension**: If user specifies `-o output.pdf`, export as PDF
3. **Context clues**: "send to printer" → PDF, "present in browser" → HTML, "share with coworkers" → PPTX
4. **If ambiguous**: Ask user: "What format would you like? (PDF, HTML, PPTX, or PNG images)"

## Input File Resolution

1. If argument provided, use that file
2. If no argument, infer from context:
   - Check for recently edited `*.md` files in conversation
   - Look for files with `marp: true` frontmatter in current directory
   - Common defaults: `deck.md`, `slides.md`, `presentation.md`
3. If still unclear, ask user

## CLI Construction

Build the appropriate Marp CLI command:

| Format | CLI Flag |
|--------|----------|
| PDF | `--pdf` or `-o file.pdf` |
| HTML | `--html` or `-o file.html` |
| PPTX | `--pptx` or `-o file.pptx` |
| PNG | `--images png` |
| JPEG | `--images jpeg` |

### Common Options (apply when relevant)

- `--allow-local-files` - Allow loading local resources
- `--pdf-notes` - Include presenter notes (PDF only)
- `--pdf-outlines` - Add PDF outlines/bookmarks
- `--theme <name>` - Override theme (default, gaia, uncover)
- `--image-scale <n>` - Higher resolution images
- `--bespoke.transition` - Enable HTML transitions

## Implementation

1. Resolve input file
2. Infer or ask for output format
3. Construct and run Marp CLI command via Bash
4. Report success with output location
5. On error, provide helpful troubleshooting:
   - Check if Marp CLI is installed
   - Verify input file exists and has `marp: true`
   - Check browser installation for PDF/PPTX

## Allowed Tools

- `Bash`: Run Marp CLI commands
- `Read`: Verify file contents and frontmatter
- `Glob`: Find Marp files in directory
