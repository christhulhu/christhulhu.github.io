---
title: Home Assistant
date: 2025-06-07
lastmod: 2025-06-17
tags:
  - tooling
  - uses
  - smart-home
  - home-server
  - deployment
  - docker
  - home-assistant
aliases:
  - /uses/home-assistant
  - /uses/mosquitto
  - /uses/zigbee2mqtt
  - /deployments/home-assistant
  - /deployments/zigbee2mqtt
  - /deployments/mosquitto
  - /docker-container/home-assistant
  - /docker-container/mosquitto
  - /docker-container/zigbee2mqtt
  - /docker-compose/home-assistant
draft: false
---

I use **Home Assistant** as my primary control panel for my smart home. 

## Setup

* **Home Assistant** as control panel for my smart home and host for automations.
* **Zigbee2mqtt** to connect Zigbee devices in my home.
* **Mosquitto** as MQTT Broker

## Deployment

* All 3 services run on my [home-server](/home-it): A small **Lenovo ThinkCentre M73 Tiny**, attached via Ethernet to my Fritz!Box
* A **Aeotec Zi-Stick for Zigbee** is plugged into my server via USB.
  * The USB dongle is mounted into the _Docker container_ of **Zigbee2mqtt** 
* All 3 services are bundled in one _Docker Compose_ definition
  * The containers for **Home Assistant** and **Zigbee2mqtt** are in _2_ Docker networks: 
    * A proxy network for ingress
    * A dedicated network for the 3 services
  * **Traefik** runs in a separate Docker Container as ingress service for all HTTP requests. It routes the traffic from external clients to the internal Docker containers.
    * **Mosquitto** needs no external access. It is used for communication between **Home Assistant** and **Zigbee2mqtt** only!

__Schematic illustration of the Docker setup:__
![Docker compose setup for Home Assistant, Zigbee2mqtt and Mosquitto](/images/docker-compose-home-assistant.png)

> I really like this setup as it showcases Docker, Docker Networks and traffic routing in an easy way.

## Zigbee2mqtt: Connected Zigbee IoT-Devices

With the **Aeotec Zi-Stick** and **Zigbee2mqtt** I avoid having multiple gateways for each vendor. I can connect devices from different vendors using just one USB-Dongle.

__Schematic illustration of my Zigbee topology:__
![Zigbee devices on Aeotec Zi-Stick](/images/zigbee2mqtt-iot-devices.png)

### Device Types

* **SONOFF**
  * **02D**: Smart thermometer / hygrometer
  * **TRVZB**: Smart thermostat 
* **IKEA**
  * **E2013**: Window sensor
  * **LED2109G6**: Smart RGB Bulb
  * **L2112**: Smart LED stripe
* **Philips**
  * **929003017102**: Hue wall switch
  * **929002398602**: Hue button

> For the sake of simplicity, I only included the device vendors and types in my network, not each device.

## Home Assistant

> **This section is a work in progress!**
> 
> I might or might not extend this section over the time...

### Services I use

- **AVM FRITZ!Box Tools**: Get information from my router, i.e. which device is currently in my home
- **Better Thermostat**: Connect my thermometer with window sensors and thermostates
- **Generic Camera**: Connect to my TP-Link cameras
- **Google Cast**: Cast to my Google Nest Mini
- **HACS**: Additional services and extensions for Home Assistant
- **MQTT**: Connect to Mosquitto and thus to Zigbee2mqtt
- **Philips Hue**: Still some bulbs directly connected to the Hue Bridge...
- **Scheduler**: Create schedules for my thermostats
- **Sun**: Useful in some automations
- **Sonos**: Control my Ikea Symfonisk
- **Spotcast**: Cast music from Spotify to my Nest Mini
- **Spotify**: Use Spotify as music library
- **Tuya**: Controll some Wifi plugs

_Schematic illustration of my Home Assistant services:_
![Home Assistant Services](/images/home-assistant-services.png)