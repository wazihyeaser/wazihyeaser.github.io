---
layout: page
title: IoT Smart Home Automation System
description: An ESP8266 home-automation system with multi-sensor monitoring, four-appliance relay control, an OLED display, and ThingSpeak cloud.
category: undergraduate
importance: 3
tech: [ESP8266, IoT]
---

<p class="project-back"><a href="{{ '/projects/' | relative_url }}">&larr; Back to Projects</a></p>

An ESP8266-based home-automation system that monitors the environment (temperature, humidity, air quality, motion), controls four appliances via relay modules, shows live data on an OLED screen, and connects to the ThingSpeak cloud for remote monitoring and control.

## System architecture

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-home/system_architecture.png" alt="System architecture">

## Features

- **Temperature & humidity** — DHT11, shown on the OLED and in the cloud.
- **Air-quality monitoring** — MQ-135 gas sensor with a configurable alarm threshold.
- **Motion detection** — PIR sensor for presence awareness.
- **OLED display** — SH1106 128×64, cycling through four data screens.
- **Four-appliance control** — relay modules for fan, light, fridge, and oven.
- **Gas safety** — automatic buzzer and exhaust fan on gas-leak detection.
- **ThingSpeak cloud** — uploads sensor data and pulls remote control commands.

## Built iteratively, in four phases

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-home/evolution_timeline.png" alt="Project evolution timeline">

Sensor reading → local control (relays + threshold logic) → cloud IoT (WiFi + ThingSpeak) → notifications.

## OLED display & sensor data

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-home/oled_display.png" alt="OLED display">

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/smart-home/sensor_timeline.png" alt="Sensor timeline with a gas-leak event">

The timeline shows normal operation with a gas-leak event that crosses the alarm threshold, automatically triggering the buzzer and exhaust fan.

## Tech stack

ESP8266 (NodeMCU) · DHT11 · MQ-135 · PIR · SH1106 OLED · relay modules · ThingSpeak cloud.
