---
title: Local DNS with PiHole
date: 2025-06-08
lastmod: 2025-06-08
tags:
  - tooling
  - uses
  - deployment
  - docker
  - pihole
aliases:
  - /uses/pihole
  - /deployments/pihole
  - /docker-container/pihole
draft: false
---

I use **PiHole** in my local network for two different reasons:
- Ad-Blocking for my network
- as a local DNS server to make the services on my home-server available by URL

> This page describes my DNS setup and wiring on a very high level!

## Key components for my local DNS setup

**PiHole**
- Handles DNS resolving of `http://localservice.home` as a `CNAME`-record to the DNS record of my home-server.
- The DNS listener `:53` is made availabe as virtual host in my network, using **Docker MacVLAN**

**Traefik**
- Handles the routing for an HTTP request URL to a **Docker Service**
- Exposes the **PiHole** Admin GUI via HTTP.
- Is the only **Docker Container** on my host with port binding `:80:80`

_Schematic Setup of PiHole and Traefik for DNS and Routing:_
![PiHole Setup](/images/pihole-dns-setup.png)


## How does it work?

- A client wants to access a service on the Home-Server.
- He types the url `http://service.home` into the address bar of his browser
- The browser sends a DNS request to **PiHole** as primary DNS in my network
- **PiHole** translates the address to the IP of the Home-Server
- **Traefik** listens on HTTP port `:80` for all HTTP requests
- **Traefik** translates the request URL to a **Docker Service** and routes the request and response accordingly.

_Schematic sequence of an http request in my network:_
![Routing Sequence with PiHole and Traefik](/images/pihole-dns-sequence.png)

## Noteworthy Aspects

- For each new service, I need to configure a `CNAME` entry in **PiHole**
- I need to add `labels` to each `docker-compose.yml` that configure the routing in **Traefik**
- All services that need to be available from external, need to be on the same **Docker Network** as **Traefik**