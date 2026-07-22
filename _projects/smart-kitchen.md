---
layout: page
title: IoT Smart Kitchen
description: An ESP8266 kitchen-safety system with gas-leak detection, motion lighting, a live web dashboard, and ThingSpeak logging.
category: undergraduate
importance: 4
tech: [ESP8266, IoT]
---

<p class="project-back"><a href="{{ '/projects/' | relative_url }}">&larr; Back to Projects</a></p>

An ESP8266-based IoT system that monitors the kitchen environment (temperature, humidity, air quality) and provides automated safety features — gas-leak detection with a buzzer alarm and motion-activated lighting — alongside a real-time web dashboard and ThingSpeak cloud logging.

## System architecture

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-kitchen/system_architecture.png" alt="System architecture">

## Features

- **Temperature & humidity monitoring** — DHT11, shown live on the dashboard.
- **Gas-leak detection** — MQ-135 triggers a buzzer alarm past a set threshold.
- **Motion-activated lighting** — a PIR sensor turns on an LED on presence.
- **Web dashboard** — an ESPDash-based responsive UI with live sensor cards.
- **Cloud logging** — ThingSpeak integration for remote monitoring.
- **Manual light control** — toggle the relay from the dashboard.

## Dashboard & sensor data

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-kitchen/dashboard_overview.png" alt="Web dashboard">

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-kitchen/sensor_timeline.png" alt="Sensor timeline with a gas spike">

The timeline shows normal operation with a gas spike that crosses the alarm threshold; the system activates the buzzer until air quality returns to safe levels.

## Tech stack

ESP8266 (NodeMCU) · DHT11 · MQ-135 · PIR · relay module · ESPDash · ThingSpeak cloud.
