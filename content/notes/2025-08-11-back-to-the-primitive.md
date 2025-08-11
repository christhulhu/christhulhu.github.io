---
title: Back to the Primitive
date: 2025-08-11
type: note
layout: single
tags:
- thought
- minimalism
series:
- Back To The Primitive
---

# Back To The Primitive

Periodically I re-evaluate stuff. I review my methodologies, tech-stack, tools and decide if I still need them or if they still fulfill my requirements. In this years cycle, I made a massive shift for a lot of things.

## Bye bye NextCloud

As I permanently work from home, I considered moving my NextCloud instance from my VPS to my home server for a long time. As I have a Wireguard VPN on my Fritz!Box, I have access to my home IT from everywhere. But during migration, I evaluated my needs. The result was simple: I need a central file storage to access from my laptop and my smartphone.

**I do not need**:
- a multi-user solution
- sophisticated sync across several devices
- bloat like calendar, bookmarks, office suite.

**What I need**:
- WebDAV for my Obsidian Vault
- File access via SFTP/Samba
- nice-to-have: A web-gui for filemanagement

So I created a simple stack with Samba, Webdav and Filebrowser. But most access to my server happens via `ssh` / `sftp`.

## Hello Terminal. Again.

As I now access my files via `ssh` primarily, I began to use tools like `ranger` or `vi` more often (again). And it feels good to use simple tools for simple tasks. No noise, no bloat, everything straight forward. Although I must admit, that I really enjoy Obsidian for note taking and PKM on my smartphone. But on my desktop, `fzf`, `ripgrep`, `fd` and `vim` do the job.

## R.I.P SpaceVIM

At the beginning I really liked SpaceVIM, a bundle of settings and plugins that put `vim` on steroids. But I do not need all the clutter. As the project abandonned anyway, I deleted the `.spacevim` directory from my computer and created a minimal `.vimrc` by myself with only a hand full of plugins:

**vim Plugins**:
- `fzf.vim`
- `nerdtree`
- `airline`

That's it!

## CGDE - This Blog!

Decluttering stuff and implementing more minimalism will have it's impact on this blog as well. It was never intended to be a "regular blog" anyway. But I really love concepts like Indie-Web or Digital Garden, so I somehow want to participate. Or just express myself online as I cannot bear social media and it's latest developments anymore...

But what does that mean? Frankly, I do not now yet. To be honest, I write notes and logs for a lot of stuff. But I do this in private in my Obsidian Vault. Most of the stuff is not intended for the public. But how can I decide what I want to post online and what to keep for myself? 

Maybe I need to re-evaluate this at the beginning. Establish a new folder in my Obsidian Vault, write blog posts for myself. And maybe some of it will be published later. Or will remain unfiltered and unpolished in my Vault. Time will tell.

But I took the chance to reduce the noise on this page. I moved some pages out of sight. And deleted some obsolete stuff. Just like in a real garden...


