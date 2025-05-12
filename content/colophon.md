---
title: "/colophon"
date: 2025-05-11
lastmod: 2025-05-11
type: page
layout: single
draft: false
description: "Technical details and background on how this site is built, maintained, and published."
aliases: ["/colophon/"]
---

This site is a reflection of my fondness for structure, documentation, and open tools. Here's a breakdown of the tech stack and philosophies behind it.

---

## Site Generator

- Built with **[Hugo](https://gohugo.io)** — fast, flexible, and Markdown-native.
- Content is written in **Markdown**, enriched with **YAML frontmatter** and a few custom shortcodes.
- Site structure follows a mix of **blog**, **digital garden**, and **manual documentation** principles.
- Source code is managed with **Git** and hosted on **GitHub**.

## Deployment

- Automated deployment using **GitHub Actions**: each `main` push triggers a Hugo build and publishes to GitHub Pages.
- Occasionally tested locally with `hugo server` before pushing.

## Theme & Styling

- Minimal, content-first [smol](https://github.com/colorchestra/smol) theme with light customizations.
- Navigation is intentionally simple — no JavaScript frameworks, no trackers, no popups.

## Tools Used

- **Editor:** [Visual Studio Code](https://code.visualstudio.com) with *Markdown Preview Enhanced* plugin.
- **PKM System:** [Obsidian.md](https://obsidian.md) — my second brain; most content starts or evolves there before being published.
- **File Sync:** [Nextcloud](https://nextcloud.com), self-hosted.
- **Note Syncing on Mobile:** Nextcloud Notes app with Markdown folder integration.

## Hosting

- **Static hosting:** GitHub Pages via custom domain.
- **DNS & Domain:** Managed via Host Europe.
- **No database**, no server-side logic — just good old HTML, CSS, and Markdown.

## Philosophy

- I prefer **offline-friendly**, **privacy-respecting**, and **minimal** tech.
- Everything I use must be **local-first**, plain-text-based if possible, and versionable.
- I'm allergic to bloat. If a tool has a loading spinner, I probably won’t use it.
- I believe in **docs-as-code**, **transparent publishing**, and the long-term value of plain files over platforms.

## Versioning & History

- I maintain changelogs and edit logs for major content areas.
- Pages like [`/now`](/now), [`/uses`](/uses), and this one are updated manually as my workflow evolves.

---

If you have questions about this site or its setup, feel free to [get in touch](mailto:chr.schmitz01@gmail.com).