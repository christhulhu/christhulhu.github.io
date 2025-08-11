---
title: Self-Organization in 2025
date: 2025-04-24
type: note
layout: single
tags: 
- task-management
- note-taking
- journaling
- vps
- home-it
---

Over the years I tried different approaches to organize my life and keep track of stuff. There are a Lot of great methodologies, but IT took me some time until I figured out what works best for me. My current workflow is a pretty simple and straight forward hybrid approach between digital and analog techniques. 

## Tasks and To-Dos

Primarily my tasks are managed digitally with [TickTick](https://ticktick.com). I keep separate lists for personal projects and errands and have shared lists with my wife for chores, groceries shopping and home related projects. This digital approach allows us to assign a task to someone, create recurring items or simply create a schedule and plan ahead.

But somehow I integrated a physical notebook in my workflow again. In the morning all tasks for today are noted down in Bullet Journal style. Any new item for today will just be added into the notebook. Only tasks for the future or that need to be migrated, are transferred to TickTick again.

This hybrid approach works very well for me, since it feels more natural and faster just to pick up a pen and write down an item instead of using an app including overhead like unlocking the phone, starting the app, choosing the right list, etc.

## Note-Taking and Journaling

In the past, I used the Bullet Journal approach for note-taking as well. But searching was always an issue for me. Dedicated apps never really worked for me until I set up my own NextCloud instance and installed the Notes app. It creates simple markdown files that can be processed with any tool of my choice, are Not vendor-locked and future prove.

To keep things even more straight forward, I create a file for the current Month and simply write down anything as unsorted list per day. Those notes can contain useful web links, random thoughts, events that happened during the day or even code snippets. Just Type it down in rapid logging. Sometimes I add emojis for better visual recognition, sometimes i extract information in dedicated files for a topic, some notes will become useless the other day which does not really matter.

Aside of those generic files, I created standalone files for dedicated topics. For example one file per book I've read, where all notes or quotes will be captured. Or one File to document my Home IT Setup. For this purpose the built-in Mermaid Support adds great value.

Working in markdown holds some limitations and for professional writing I prefer asciidoc, but this forces me to keep my workflow as simple as possible. I think it is this simplicity that made me stick to the process of consistent note-taking and journaling.

## File Storage and Cloud Storage

To be honest, this is currently a mess with me. For Most documents and shared access with my wife, I use Google Drive with paid plan for 100 GB storage. This hast done a great Job, especially when collaborative work with other parties was required. But as already mentioned, I have an own NextCloud instance on a VPS as well, were I have some files too. And in my Home-IT there is a dedicated NAS. Due to the Energy consumption, it is offline most of the time and mostly used for cold backups.

I think in the future I will consolidate this a little bit more. But currently I'm not sure whether I will reduce my NextCloud to notes only, ditch Google Drive in favour of NextCloud or even consider another cloud storage provider for files.

## Source Code Management

Somehow this is a mess as well. I really enjoy working with Git and having versions of my files, regardless of content. It can be source code, notes, anything that is stored as plain text. I use [Github](https://github.com/christhulhu) for stuff that should be publicly available. There is the code for this website (obviously) and my other project [Scolohub.com](https://scolohub.com) as well as the archive of my old webzines. But when it comes to private coding projects, I prefer to have things under control. So I currently have a [Gitea](https://about.gitea.com/) instance on my VPS for those things. This holds any configurations for my Home Server, my VPS itself and anything I coded, ranging from small batch processing stuff to little Webapps for personal use. I thing it is not really required to have this Git server online available and I really consider moving it from my VPS to my local Home Server.

## Home Server

As I previously mentioned my Home Server, I think I should give a brief overview of it's current role in my setup. Although it currently houses a [Bookstack](https://www.bookstackapp.com/) and a [Homebox](https://hay-kot.github.io/homebox/) instance, I do not really use them. I thought having a wiki or an inventory system at hand could be useful, but somehow I sticked to plain markdown notes in my NextCloud. I think I will decommission those two apps any time soon.

Another app for self organization is [Paperless NGX](https://docs.paperless-ngx.com/) which keeps some redundant documents that are already stored in my Google Drive. Until now I could not convince my wife to use Paperless since she does not see any advantage in this document management system and is used to the file-and-folder based approach of Google Drive. 

Nevertheless, my Home Server still adds some benefits to my home as it runs [Home Assistant](https://www.home-assistant.io/) and [Zigbee2mqtt](https://www.zigbee2mqtt.io/) for our smart home components, [PiHole](https://pi-hole.net/) as DNS and ad-blocker as well as some personal Webbapps, for example a dedicated journal about my centipede husbandry.

## VPS

I have a very small VPS that serves two purposes: Making my NextCloud (and currently my Gitea) available from the Internet and serving offside storage for my Home Server backups. 

Since my DSL Router offers Wireguard VPN out of the box, I consider moving everything into my Home Server and keep the VPS for backups only...

## NAS

As my NAS with conventional HDDs consumes more energy as my small Home Server with SSDs, I rarely use it anymore. It is used for occasional backups, keeps some older photos and documents and my digital music collection. Before I set up my Home Server, it was used as Docker host as well, but my current server is way more efficient both in performance as well as energy consumption.
