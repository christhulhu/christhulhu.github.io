---
title: Hugo
date: 2025-05-19
lastmod: 2025-05-19
tags:
  - tooling
  - site
  - publishing
  - uses
aliases:
  - /uses/hugo
draft: false
---

[Hugo](https://gohugo.io) is the static site generator I use to build and publish this website. It’s fast, flexible, and fits my preference for writing in plain text and versioning everything in Git.

## Why I Use Hugo

- **Blazing fast**: Even large sites build in milliseconds.
- **Markdown-first**: I write everything in `.md` — whether it’s notes, changelogs, project logs, or pages like this one.
- **Git-friendly**: Full version control over everything, including metadata and structure.
- **Custom workflows**: I can prepare posts and notes in any text editor from `vim` to `vscode` or in [Obsidian](/uses/obsidian) and publish via GitHub when I’m ready.
- **Great theming**: From ready-to-go solutions over customizations of existing themes to fully homebrewn ones, everything can be done in no time.
- **Flexibility**: Tags, custom taxonomies, individual page types and layouts and enhancements with `yaml` data files, content management in steroids out of the box with no plugins required.

## How I Use It

- **Theme**: 
	- This page: [Smol](https://github.com/colorchestra/smol) — minimal and no-frills. Perfect for a digital garden aesthetic. But with minor customizations.
	- [Scolohub](https://scolohub.com): Hugo Docs - Bringing a documentation template to terraristics.
	- [TheNocturnalSilence](/projects/thenocturnalsilence_de): A fully selfmade theme that gave every page an unique touch. 
- **Hosting**: GitHub Pages with CI/CD via GitHub Actions.
- **Frontmatter**: I standardize metadata to help keep things organized, taggable, and filterable.
- **Data Types**: Generating content with `yaml`, I love it `<3`

## Limitations

- Steep learning curve if you are not familiar with markdown, git or the commandline. 

## TL;DR

Hugo supports my philosophy of sustainable, low-maintenance publishing. It gives me full control, no distractions, and a workflow that integrates naturally with how I take and manage notes and try to live GitOps.