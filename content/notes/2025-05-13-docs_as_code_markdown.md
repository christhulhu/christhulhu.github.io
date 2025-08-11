---
title: Taking Notes & Writing Documentation with Markdown
date: 2025-05-13
lastmod: 2025-05-13
draft: false
type: note
layout: single
tags:
  - markdown
  - note-taking
  - documentation
  - docs-as-code
series:
  - Docs as Code
---

# Documentation and Note-Taking with Markdown: A Practical Guide

Markdown has become the de facto standard for lightweight text formatting, especially in tech-focused environments. This guide provides an overview of Markdown, its variants, how it compares to [AsciiDoc](/notes/docs_as_code_asciidoc/), tools and services that support it, and best practices for writing clean, extensible Markdown documents.

---

## What Is Markdown?

Markdown is a **lightweight markup language** created by John Gruber in 2004, designed to be **readable in plain text and easily convertible to HTML**. It uses simple punctuation and symbols to format text — for example:

```markdown
# Heading 1
## Heading 2

**Bold** and *Italic*

- Lists
- Are
- Simple

[Links](https://example.com)
```

The primary goal of Markdown is **simplicity**. It allows authors to write content without the overhead of complex formatting tags.

---

## Flavours and Differences: Which Markdown Standard to Use?

### Common Flavours

There is no single Markdown standard. Instead, several **flavours** or implementations have evolved:

| Flavour                        | Description                                                                                     |
|--------------------------------|-------------------------------------------------------------------------------------------------|
| **Original Markdown**              | Created by Gruber; minimalistic, lacks tables, footnotes, etc.                                  |
| **GitHub Flavored Markdown (GFM)** | Extends Markdown with tables, task lists, fenced code blocks, and autolinks. Widely supported.  |
| **CommonMark**                     | An attempt to create a consistent, unambiguous spec. Well-structured and extensible.            |
| **Pandoc Markdown**                | Very powerful; includes citations, footnotes, LaTeX math, and more. Ideal for academic writing. |

### Which Standard Should You Use?

- **General writing and GitHub projects:** Use **GFM**. It's widely supported and flexible.
- **Publishing and academic writing:** **Pandoc** is extremely powerful.
- **Strict consistency:** **CommonMark** is clean and reliable.

> [!Tip]
> Always check what flavour your tool or platform uses, especially if you rely on advanced features like tables or checkboxes.

---

## Markdown vs AsciiDoc: Why Choose Markdown?

| Feature           | Markdown                    | AsciiDoc                           |
|-------------------|-----------------------------|------------------------------------|
| Syntax            | Minimal, easy to learn      | More verbose but more powerful     |
| Tooling           | Supported almost everywhere | Fewer tools, more niche            |
| Complexity        | Lightweight                 | Better for large technical docs    |
| Community/Support | Broad, mainstream           | Used in some developer communities |
| Extensibility     | Needs plugins/front-matter  | Has built-in semantic structures   |

### Advantages of Markdown

- Easy to **read and write** even in raw form
- Excellent support across **editors and platforms**
- Ideal for **notes, documentation, and blogging**
- Easily converted to HTML, PDF, DOCX (via tools like **Pandoc**)

> For most users, Markdown hits the sweet spot between **functionality** and **simplicity**.

---

## Tools and Services That Support Markdown

### Editors

- **VS Code** with extensions like *Markdown Preview Enhanced*
- **Typora**: WYSIWYG-style markdown editor
- **Obsidian**: Knowledge management with Markdown vaults
- **Zettlr**, **Logseq**, **Joplin**

### CLI / Conversion

- **Pandoc**: Converts Markdown to HTML, PDF, LaTeX, DOCX
- **markdownlint**: Linting for consistent style

### Online Services (selection)

| Platform         | Markdown Support                      |
|------------------|---------------------------------------|
| GitHub           | Full GFM support                      |
| GitLab           | GFM + extras                          |
| Notion           | Imports/exports MD                    |
| Obsidian Publish | Markdown-native                       |
| Stack Overflow   | Partial MD syntax                     |
| Reddit           | Custom MD parser                      |
| Hugo / Jekyll    | Static site generators using Markdown |

> [!Tip]
> Many platforms support Markdown in **comments, issues, wikis, and documentation**.

---

## Best Practices for Writing in Markdown

1. **Use headings hierarchically** (`#`, `##`, `###`) for clear structure.
2. **Keep lines short** (~80–120 characters) for better diffing and readability.
3. **Use lists and tables sparingly**; too much structure can reduce clarity.
4. **Prefer inline links** (`[text](url)`) over raw URLs.
5. **Use fenced code blocks** (3 times Backtick) with language hints for syntax highlighting.
6. **Separate content from style**; don't rely on manual formatting.
7. **Stick to one flavour per project** to avoid compatibility issues.
8. **Validate and preview** regularly using your target platform or tool.

---

## Extending Markdown with Front Matter

Many tools (like **Hugo**, **Jekyll**, or **Obsidian**) use **YAML front matter** to add metadata to Markdown files. Example:

```yaml
---
title: "My Document"
date: 2025-05-13
tags: [documentation, markdown]
draft: false
---
```

This front matter doesn't render in the final output but can be used for sorting, filtering, publishing, and more.

### Good Uses of Front Matter

- Blog posts or website content
- Project documentation with clear metadata
- Obsidian/Zettelkasten workflows

### Bad Uses

- Storing data that should be in a database or separate config
- Embedding too much logic or rendering info in the front matter

### Ugly Pitfalls

- Mixing front matter formats (YAML vs TOML vs JSON)
- Creating long, complex front matter blocks with nested structures
- Using non-standard fields that your tools don’t recognize

> Keep front matter **simple, relevant, and tool-compatible**.

---

## Conclusion

Markdown is a powerful, flexible format for note-taking and documentation, made even more effective with the right tools and habits. Whether you're managing a personal Zettelkasten, writing software docs, or publishing content online, Markdown offers a balance of readability, simplicity, and extensibility.
