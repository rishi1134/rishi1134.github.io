---
title: "Pi-Eye: Embedded Assistive Vision System for Visual Impairments"
collection: talks
permalink: /talks/pieye
level: Undergraduate
year: "2020"
category: edge-systems
order: 2
header:
  teaser: /images/pieye_block.png
teaser: /images/pieye_block.png
tags: ["Assistive CV", "Embedded Systems", "TensorFlow Edge", "Interactive Vision"]
affiliation: "Embedded Systems Coursework (ECE4003) | VIT"
videourl: "https://drive.google.com/file/d/1UOnIgLff9UmnFGvDaFxGuVn7YWzoan8s/view?usp=sharing"
excerpt: "Interactive assistive vision wearable for individuals with visual impairment and color vision deficiency, featuring dual-mode power-adaptive object detection and tactile pointer-guided color recognition."
---

## Overview

Pi-Eye is an assistive edge-vision prototype engineered to assist individuals with mild to severe visual impairments and severe color vision deficiency (dichromacy or complete absence of cone photoreceptor cells). The wearable system processes real-time camera frames and provides synthesized auditory speech feedback describing object identities and colors.

The project was developed as part of the advanced coursework *ECE4003 - Embedded Systems Design* at Vellore Institute of Technology.

- **Demonstration Video**: [Interactive Hardware Demo Video](https://drive.google.com/file/d/1UOnIgLff9UmnFGvDaFxGuVn7YWzoan8s/view?usp=sharing)

---

## System Architecture

![System Block Diagram](../../images/pieye_block.png)
*Figure 1: End-to-end hardware and software pipeline, illustrating camera capture, interrupt state machine, neural inference, and audio DAC output.*

---

## Power-Adaptive Dual-Mode Operation

To manage strict thermal and battery constraints on embedded edge hardware, the system implements an adaptive state machine with two operating modes:

### 1. MinMode (Power-Conservative Interrupt Mode)
- **Activation**: Automatically engaged when system battery level falls below an established operational threshold.
- **Workflow**: The system remains in an ultra-low-power idle state until the user triggers a physical switch interrupt. Upon receiving the interrupt, the camera captures a single frame, executes a lightweight TensorFlow object detection model, identifies dominant color clusters within bounding box boundaries, and synthesizes audio descriptions through the DAC.

### 2. MaxMode (Active Interactive Pointer Tracking)
- **Activation**: Engaged during nominal battery levels.
- **Workflow**: Continuous video frame streaming into a circular frame buffer. The user points to an object of interest using an ergonomic pointer pen. An interrupt triggers localized frame extraction; a dedicated convolutional neural network identifies the pointer tip coordinates, segments the target region of interest, and executes real-time classification to deliver immediate auditory feedback of the targeted object.

---

## Key Engineering Takeaways

- Designed an interrupt-driven embedded system minimizing idle compute consumption by over 60%.
- Integrated lightweight neural object detection and localized color space analysis on embedded ARM hardware.
- Delivered an intuitive, hands-on assistive interface providing actionable auditory feedback for visually impaired users.
