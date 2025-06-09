---
title: Home-Server Docker Setup
date: 2025-06-09
lastmod: 2025-06-09
tags:
  - tooling
  - uses
  - deployment
  - docker
aliases:
  - /home-server/docker
draft: false
---

> [!tldr] **All services on my Home-Server run as Docker container.**
> 
> For external access, I use **Traefik** as ingress router. Other ports are made available with Docker MacVLAN.

## Basic Setup
* All services are bundled as `docker-compose.yml`
* **Traefik** is my ingress router. 
  * with `labels` I configure the routing with Traefik
  * Traefik is the only Container with a port-binding to the host: `:80:80`
* A dedicated Docker Network `webproxy` is used for all services that should be available via `http`
* All services that are required internally (i.e. databases) are only available in a dedicated network for the `docker-compose` setup and not reachable from outside.
* **PiHole** is used for local DNS.
  * PiHoles DNS listener is made availabe via **Docker MacVLAN** on a dedicated IP address
  * PiHole Admin GUI is made available with Traefik

_Schematic illustration of my Home-Server Docker Setup:_
[![Home-Server Docker Setup](/images/home-server-docker-setup.png)](/images/home-server-docker-setup.png)
