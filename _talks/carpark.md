---
title: "EasyGo: Edge Vision-Based Real-Time Parking Space Detection"
collection: talks
permalink: /talks/easygo
level: Undergraduate
year: "2020"
category: edge-systems
order: 3
header:
  teaser: /images/easygo_detection.png
teaser: /images/easygo_detection.png
tags: ["Edge Inference", "Real-Time Object Detection", "YOLO / MobileNet", "Raspberry Pi"]
affiliation: "IoT & Edge Computing Coursework (CSE3009) | VIT"
codeurl: "https://github.com/rishi1134/EasyGo"
excerpt: "Edge vision-based smart parking system deploying MobileNet-SSD and YOLOv2 on Raspberry Pi 3B+ for real-time slot occupancy tracking, polygon ROI mapping, and cloud state telemetry."
---

## Overview

Urban parking congestion significantly increases transit time, fuel consumption, and urban emissions. Traditional smart parking solutions require expensive in-ground inductive loops or ultrasonic sensors embedded in every parking stall, leading to prohibitive installation and maintenance costs.

**EasyGo** is an edge computer vision solution that eliminates dedicated in-ground hardware by using a single monocular camera paired with an edge microprocessor to continuously detect, track, and report individual parking slot occupancies in real time.

- **Source Code**: [GitHub Repository (rishi1134/EasyGo)](https://github.com/rishi1134/EasyGo)

---

## System Pipeline & Technical Details

1. **Edge Neural Detection**: Deployed quantized MobileNet-SSD and lightweight YOLOv2 object detection models on a Raspberry Pi 3B+ edge unit.
2. **Polygon Region-of-Interest (ROI) Mapping**: An administrative calibration module allows one-time polygonal demarcation of parking stalls. Real-time vehicle bounding boxes are mapped to pre-calibrated stall coordinates using intersection-over-union (IoU) spatial thresholds.
3. **Telemetry & Synchronization**: Detection state updates are pushed to a centralized cloud database, enabling real-time slot reservation and availability routing via web and mobile interfaces.

![Detection Screenshot](../../images/easygo_detection.png)
*Figure 1: Real-time vehicle detection and parking stall occupancy tracking running on the edge processing pipeline.*
