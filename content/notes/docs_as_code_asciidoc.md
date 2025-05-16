---
title: Docs as Code with AsciiDoc
date: 2025-05-13
lastmod: 2025-05-13
draft: false
tags:
  - documentation
  - asciidoc
  - docs-as-code
series:
  - Docs as Code
---
# Writing Documentation as Code with AsciiDoc

## What is AsciiDoc?

**AsciiDoc** is a lightweight markup language that allows you to write documentation in plain text. It is designed to be human-readable and supports features like section headers, formatting, tables, links, images, callouts, and much more. AsciiDoc documents can be converted to various output formats such as HTML, PDF, DocBook, and EPUB using tools like **Asciidoctor** or **Pandoc**. AsciiDoc can also be included in toolchains like the **Maven** build tool.

> Official AsciiDoc documentation: https://docs.asciidoctor.org/asciidoc/latest/

## Why Use AsciiDoc Instead of Markdown?

While [Markdown](/notes/docs_as_code_markdown/) is simpler and widely used, AsciiDoc offers several advantages for technical documentation:

- **Semantic richness**: AsciiDoc supports more complex content like footnotes, tables, callouts, and admonitions out of the box.
- **Standardized syntax**: Markdown exists in different flavors with different features. But AsciiDoc is standardized.
- **Modular documentation**: Easier inclusion of content from other files.
- **Consistent output**: With tools like Asciidoctor PDF, your output is predictable and customizable.
- **Documentation as code**: AsciiDoc integrates well with version control and CI/CD pipelines.

---

## Setting Up AsciiDoc in the Terminal

To use AsciiDoc in your terminal, install the `asciidoctor` tool and recommended plugins:

### Prerequisites

- Ruby (2.5 or newer)
- RubyGems

### Installation

```bash
# Install Asciidoctor
gem install asciidoctor

# Install PDF converter plugin
gem install asciidoctor-pdf

# Install diagram support
gem install asciidoctor-diagram

# (Optional) Syntax highlighter support
# Rouge is used by default, but you can also install Pygments
```

### Usage

```bash
# Convert to HTML
asciidoctor mydoc.adoc

# Convert to PDF
asciidoctor-pdf mydoc.adoc

# Ensure diagrams and syntax highlighting work
asciidoctor -r asciidoctor-diagram mydoc.adoc
```

> [!info]
> Some Linux distributions offer official packages that can be installed with the OS package manager. For example for Ubuntu you can install everything with
> `apt install asciidoc asciidoctor ruby-asciidoctor-pdf ruby-asciidoctor-plantuml`

---

## Setting Up AsciiDoc and Plugins in VSCode

1. **Install the AsciiDoc plugin**
   - Search for `Asciidoctor` in the Extensions Marketplace and install it (recommended: `asciidoctor.asciidoctor-vscode`).
2. **Enable diagram support**
   - The extension will pick up diagrams if Asciidoctor Diagram is installed.
3. **Configure PDF output**
   - In VSCode, use the command palette to run: `Asciidoctor: Export document as PDF`
   - This requires `asciidoctor-pdf` installed globally (via `gem`).
4. **Live preview**
   - Open your `.adoc` file and use the preview pane (Right-click → "Open Preview to the Side").

---

## Basic Document Structure

Use a structured folder layout to separate content, includes, and diagrams:

```
docs/
├── index.adoc
├── includes/
│   ├── intro.adoc
│   ├── setup.adoc
├── diagrams/
│   ├── architecture.puml
│   ├── flow.svg
```

In `index.adoc`:

```adoc
= Project Documentation
:toc: macro
:toclevels: 2
:sectnums:

include::includes/intro.adoc[leveloffset=+1]
include::includes/setup.adoc[leveloffset=+1]
```

Diagrams directly in a document:

```adoc
[plantuml, diagrams/architecture, svg]
----
@startuml
Alice -> Bob: Hello
@enduml
----
```

Include external diagrams in a document:

```adoc
[plantuml]
----
include::diagrams/diagram.puml[]
----
```

---

## Best Practices for Writing Docs as Code with AsciiDoc

- **Keep it modular**: Use `include::[]` directives for different sections.
- **Use version control**: Track documentation changes alongside code.
- **Validate regularly**: Run Asciidoctor in CI to ensure formatting and structure.
- **Use attributes**: Define and reuse variables (e.g., version numbers).
- **Separate content and styling**: Customize styling via PDF themes or CSS for HTML.
- **Document diagrams**: Place source files like `.puml` next to generated diagrams.
- **Write for the reader**: Use clear language, consistent formatting, and headings.

## Conclusion

AsciiDoc is a powerful tool for managing technical documentation as code. With features tailored for complex documentation, it surpasses Markdown in many aspects and integrates well into developer workflows. Setting it up with VSCode and using terminal tools allows you to build professional, maintainable documentation efficiently.