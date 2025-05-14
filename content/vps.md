---
title: /vps
date: 2025-05-13
draft: false
tags:
  - infrastructure
  - self-hosting
  - linux
  - vps
aliases:
  - /vps
  - /infra/vps
---

I've been running a self-managed VPS for several years. It's a stable cornerstone for a range of personal and semi-public projects. I maintain it myself, mostly via SSH, and keep things minimal, modular, and under control. 

### Main Purpose

Although I could host everything on my home server, I operate some services on my VPS that I want to be available from the internet to be accessed everywhere. Additionally I take advantage of the in-place snapshot and backup features of my provider.

> Private projects and apps that do not need to be available on the internet are part of my [/home-it](/home-it)

### Hosting Provider

Currently hosted at: **Strato**  
Type: VPS Entry Linux VC2-4 (2 vCPU / 4 GB RAM / 120 GB SSD)
Costs: 4 EUR / month

> Previously: HostEurope – but the cheap entry level packages from Strato totally fit my needs and saved me some bucks.

DNS: **HostEurope**
Different A-Recods for hostnames to route between this Github Pages hosted homepage and my VPS that is reachable by different sub-domains.

### OS & Stack

- **OS**: Rocky Linux 9.5 (Blue Onyx)
- **Access**: SSH with key-based auth, no password login
- **Services**:
  - Docker (all apps are containerized)
  - Fail2Ban, firewalld, automatic security updates

### Hosted Projects

- **Traefik** A reverse proxy to access my services running in Docker containers
- **NextCloud**: A Docker Compose powered setup of the NextCloud App, MariaDB and Reddis.
- **Gitea** A very lightweight Git server for my private code, notes, configurations, that I do not want to be available on Github.

### Philosophy

I enjoy knowing what runs where and how. While I'm not a DevOps engineer by trade, managing my own VPS lets me stay close to the metal, and it supports my principles of independence and resilience — especially for things like file synchronization, source code management, note archives, reference collections, and documentation.

### Maintenance Habits

- Monthly updates and security audits

