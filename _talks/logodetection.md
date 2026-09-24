---
title: "Logo Detection and Analysis on Mobile Edge Devices"
collection: talks
permalink: /kala/logodetection
level: Undergraduate
year: "2021"
category: edge-systems
order: 1
header:
  teaser: /images/fyp_res.png
teaser: /images/fyp_res.png
tags: ["Object Detection", "Model Optimization", "ArmNN", "Edge Deployment", "Mobile Vision"]
affiliation: "Undergraduate Capstone | PlaEye LLC & VIT"
videourl: "https://drive.google.com/file/d/178aRTvM15KBOs9cgE2qk3s8adQEd7m30/view?usp=drive_link"
excerpt: "Mobile brand logo detection system targeting the LogoDet-3k benchmark, tackling severe class imbalance via scaled loss formulations and optimized for arm64-v8a mobile edge inference with ArmNN."
---

## Overview

Brand logo detection in unconstrained mobile captures is a challenging problem in computer vision due to extreme class imbalances across commercial brands, severe variations in scale, perspective skew, and rigid latency constraints on mobile edge processors.

This project was developed as my undergraduate capstone project in collaboration with PlaEye LLC and advised by Prof. Sathiya Narayanan S. (VIT). We engineered an end-to-end brand recognition and analysis system capable of real-time multi-brand detection on embedded ARM devices.

- **Demonstration Video**: [Watch Demo Video (Google Drive)](https://drive.google.com/file/d/178aRTvM15KBOs9cgE2qk3s8adQEd7m30/view?usp=drive_link)

---

## Problem & Technical Challenges

1. **Extreme Class Imbalance (Long-Tail Distribution)**: Logo datasets (such as LogoDet-3k with 3,000 categories) exhibit severe head-to-tail frequency skew, where common brands dominate training while niche brands suffer low recall.
2. **Arbitrary Scale & Occlusion**: Logos appear on clothing, packaging, billboards, and consumer goods at unpredictable scales and orientations.
3. **Mobile Edge Constraints**: Running real-time object detection models on ARM-based mobile processors without cloud offloading requires strict memory footprint and compute optimization.

---

## Technical Approach

### 1. Imbalance-Aware Loss Formulation
To counteract gradient suppression from dominant classes, we incorporated class-scaled loss functions (focal / frequency-weighted cross-entropy):
$$L_{\text{cls}} = -\alpha_t (1 - p_t)^\gamma \log(p_t)$$
where $\alpha_t$ dynamically balances class rarity and $\gamma$ focuses learning on hard, ambiguous logo samples.

### 2. Targeted Data Augmentation
Implemented geometric perspective warping, color jitter, and cut-and-paste logo composition into diverse natural background contexts, significantly enhancing generalization across diverse lighting conditions.

### 3. Edge Compilation with ArmNN
- Converted trained neural network weights for deployment using the **ArmNN** acceleration library.
- Targeted mobile ARMv8-A architecture (`arm64-v8a`), utilizing NEON SIMD vectorization and layer fusion to achieve low inference latency on edge devices.

---

## Results & Visualizations

![Capstone Poster](../../images/FYP_Poster.png)
*Figure 1: Capstone research poster detailing system architecture, loss formulations, and mobile deployment.*

![Detection Results](../../images/fyp_res.png)
*Figure 2: Qualitative brand logo detection results across cluttered scenes, showing robust localization and classification across varying scales.*
