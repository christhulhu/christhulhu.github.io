---
title: /home-it
date: 2025-05-13
draft: false
tags:
  - home-it
  - self-hosting
aliases:
  - /infra/home-it
---
My home network is a blend of practicality, curiosity, and mild overengineering — optimized for control, documentation, and resilience.

### Philosophy

I like knowing what's running in my environment, logging it properly, and keeping things modular and comprehensible. I document **IP addresses, MACs, services, topologies, and configurations** in [Markdown](/notes/docs_as_code_markdown/) (with diagrams via PlantUML or Draw.io).

### Core Components

- **Router**: Fritz!Box 7530 AX
	- Role: Gateway, Router, WiFi-AP, DHCP, Wireguard VPN Server 
- **Network layout**: Star topology with a mix of Ethernet and WiFi
- **Home-Server**: Lenovo ThinkCentre M73 Tiny
	- Role: Docker Host, Automations, Playground for homebrewn webapps
	- Powered with _Aeotec Zi-Stick for Zigbee_ connectivity.
- **NAS**: Synology Diskstation 416play
	- Role: Data store and cold backups
- **Smart-Home Bridge**: Philips Hue Bridge
	- Note: currently kind of a legacy device as I move to Zigbee2Mqtt and want to implement a cloudless smart home
- **Access Points**: Currently no additional APs in use. The Fritz!Box serves a pretty good coverage in our home, basement and even large parts of our garden.

Everything with **static DHCP leases**, even all client devices, documented via MAC and hostname in a central `.md` file.

### Self-hosted Applications (via Docker)

- **Traefik**: Reverse Proxy to access Docker Container
- **PiHole**: Central ad-blocking and DNS for local network
- **Dashy**: Dashboard for my apps and services and starting page for my browser
- **Home Assistant** / **Zigbee2mqtt** / **Mosquitto**: Smart Home Hub. 
- **Beaver Habit Tracker**: A self-hostable webapp in the style of Loop Habit Tracker
- **Paperless NGX**: Powerful document management - but currently not really implemented in my workflows
- To be decommissioned: **Bookstack**: A personal wiki. Was a nice try, but i stick to simple Markdown files
- To be decomissioned: **HomeBox**: An inventory management application. Same as for Bookstack: I prefer flat Markdown.

### Maintenance

- Updates for both the OS and running Docker Containers are implemented as **Ansible Playbooks**
- **Backups** from my home server happen daily with `rsync` as `cron`-job
  - More on [#backup-strategy](/tags/backup-strategy/)
- All configurations on my home server are in a `git`-repository and versioned with every change

### Documentation & Monitoring

- All services and configs are documented in Obsidian / [Markdown](/notes/docs_as_code_markdown/) 
- Diagrams: PlantUML, Draw.io    
- Configuration is versioned with Git
- Any manual maintenance task is managed with TickTick 

### Projects in Progress

- Home automation ideas and troubleshooting
- Implementing more minimalism in my setup
- Testing Home Assistant Voice hardware to substitute "Hey Google" in our home.

---

> I maintain this network like a mini homelab — but always with a practical mindset. No Kubernetes, no overkill. Just good Linux hygiene and solid Docker practices.

For a more cloud-based view of my infrastructure, see [/vps](/vps).
