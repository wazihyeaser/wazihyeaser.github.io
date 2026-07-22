---
layout: page
title: Bluetooth-Controlled Car with Obstacle Avoidance
description: A 4WD Arduino car driven over Bluetooth from a phone, with ultrasonic obstacle avoidance and a browser-based simulator.
category: undergraduate
importance: 1
tech: [Arduino, Embedded, Robotics]
---

<p class="project-back"><a href="{{ '/projects/' | relative_url }}">&larr; Back to Projects</a></p>

A 4WD Arduino car controlled via Bluetooth from a phone app, with ultrasonic obstacle avoidance. The car automatically stops when an obstacle is detected within 15 cm, while still allowing the user to reverse away safely. A web-based 2D simulator lets you demo the whole thing without any hardware.

## System architecture

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/bluetooth-car/system_architecture.png" alt="System architecture">

## Features

- **Bluetooth remote control** — forward, backward, left, right, and stop from a phone app.
- **Ultrasonic obstacle avoidance** — an HC-SR04 sensor detects objects within 15 cm.
- **Auto-stop with safe reverse** — the car halts on detection but still accepts a backward command to escape.
- **4WD skid-steering** — tank-style turning through differential motor control.
- **Web simulator** — an interactive 2D demo in the browser, no hardware required.

## Simulator

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/bluetooth-car/simulator_preview.png" alt="Simulator preview">

A Flask + HTML5-Canvas simulator reproduces the car's physics: drive with the arrow keys and watch the ultrasonic sensor cone turn yellow and red as it approaches obstacles, triggering the auto-stop in real time.

## Skid-steering

<img class="img-fluid rounded z-depth-1" src="/assets/img/projects/bluetooth-car/motor_diagram.png" alt="Motor layout and turning">

The left-side motors (M1/M2) and right-side motors (M3/M4) rotate independently; turns are produced by driving the two sides in opposite directions.

## Tech stack

Arduino Uno · Adafruit Motor Shield v1 · HC-SR04 ultrasonic sensor · HC-05 Bluetooth module · Flask + HTML5 Canvas (simulator).
