---
layout: archive
title: ""
permalink: /multipanna/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* **M.S. in Computer Science and Engineering, University at Buffalo, 2024-26**
  - Grade: 3.95/4.0
  - Research Track with specialization in Computer Vision and Deep Learning
  - Advisor: Prof. Junsong Yuan
  - Courses: Deep Learning, Reinforcement Learning, Computer Vision, Machine Learning, Parallel and Distributed Processing, Information Retrieval, Algs for Modern Computing Systems
* **B.Tech. in Electronics and Communication Engineering, Vellore Institute of Technology, 2017-21**
  - Grade: 9.48/10.0
  - Courses: Applied Linear Algebra, Computer Communication Networks, Data Structures and Algorithms, Digital Image Processing, Embedded System Design, Probability Theory and Random Processes, Statistics for Engineers

Patents and Publications
======
*  **Rishikesh Bhyri** et al., “Chain-of-Look Spatial Reasoning for Dense Surgical Instrument Counting” IEEE/CVF Winter Conference on Applications of Computer Vision (WACV), 2026. (Accepted) [(Preprint)](https://rishi1134.github.io/files/wacv26_preprint.pdf)
* Multi-Agent Computer Vision system & methods for automated object counting, classification and tracking. USPTO Application No. 63/851,812. Status: Patent Pending. 

Research Experience
======
* **Graduate Research Assistant, Oct 2024 - Present**
  * The Research Foundation for SUNY, Buffalo, NY
  * Duties included: 
    - **High-Density Object Counting (CountGD Extension)**: Engineered a novel counting framework extending CountGD (GroundingDINO, Swin-B, BERT). Integrated class-specific learnable tokens and designed a domain-specific loss function to enhance spatial reasoning in dense clusters, achieving a state-of-the-art **Mean Absolute Error (MAE) of 0.88**.
    - **Surgical Instrument Instance Segmentation**: Developed a robust pipeline for low-to-medium density instrument segmentation. Benchmarked and fine-tuned Mask R-CNN, Mask2Former, and SAM 3, achieving **90% mAP** on the surgical dataset.
    - **Density-Adaptive Mobile Deployment**: Built an Android application for real-time inference that utilizes a custom region proposal network to dynamically route image patches to either the segmentation model (low density) or the counting model (high density).
    - **Performance Optimization**: Achieved a peak end-to-end latency of 0.32s (vs. 25.12s human counting) on mobile hardware. Reduced manual effort by 99% while maintaining high-fidelity detection visualizations.
  * Supervisor: Dr. Junsong Yuan, Dr. Peter CW Kim

* **Computer Vision Intern, Jan 2021 - June 2021**
  * PlaEye LLC
  * Duties included: 
    - **Logo Detection and Analysis in Images**: Developed a mobile-based brand analytics system for logo detection and classification using the LogoDet-3k dataset, optimized for arm64-v8a devices with ArmNN. Addressed challenges in dataset imbalance and diverse image features by implementing scaled loss functions and class augmentations. [(Link)](https://rishi1134.github.io/kala/logodetection)
    -  Automatic Calibration of Tennis Court Images: Created a novel algorithm for automated tennis court calibration using Homography and Cross ratios to overcome single-view calibration limitations arising from elusive feature points in occluded views. [(Link)](https://rishi1134.github.io/kala/courtcalib)
  * Supervisor: Mr. Venkat Yellepeddy

Professional Experience
======
* **Machine Learning Intern, May 2025 - Aug 2025**
  * Mercedes-Benz R&D (MBRDNA), San Jose, CA
  * Duties included:
    Autonomous Driving
    - Optimized inference by exploring **CUDA Graphs** with **Nsight Systems**, trimming CPU launch overhead and **cutting latency 20%**. 
    - Drove **4× faster inference** via INT8 **implicit and explicit quantization**. 
    - Built a C++/CUDA utility to inspect TensorRT engine weights and automate network-pruning sweeps. 
    - Implemented **unified-memory zero-copy** paths and custom GPU pools, **lowering peak GPU use 18%** and eliminating two memcpy calls per frame. 
    - Proved bit-exact **determinism** at runtime & layer level; stress-tested execution contexts to meet **ASIL-D safety**.
    - Designated as Primary Inventor for **2 patents** (currently in filing stage).
  * Mentor: Mr. Jalpesh Bhadra

* **Graduate Student Assistant - Grader, Jan 2025 - May 2025**
  * University at Buffalo, Buffalo, NY
  * Duties included: Course Grader for 'CSE574 Intro Machine Learning', evaluating student quizzes and assignments
  * Supervisor: Dr. Asif Imran

* **Software Engineer, July 2021 - July 2024**
  * Citi (CSIPL, Citigroup), Chennai, India
  * Duties included: 
    - Co-owned and led the development of a web-based end-to-end tool initiative for data creation and conditioning,
 reducing the time and effort required for data handling. Engineered the tool using ReactJS and NodeJS, optimizing
 test data creation and conditioning workflows
    - Developed API layers in .NET using minimal-API, exposing Selenium-C# automation functionalities and enabling
 remote headless execution which **decreased data creation time by 5x**, reduced cross-team dependency and **turnaround time by 80%**
    - Designed C# automation scripts for Fund Transfer module, **increasing the test coverage** for 7 market countries **by
 50%** and **saving cost** in licensing tools **by 30%**

Honors & Awards
======
* Best AI/ML Project, UBHacking'24, Nov 2024
  * Won the ‘Best AI/ML Project’ award at UBHacking’24 for developing an AI-powered, context-aware bookmark manager extension for Chrome

* Awarded a top rating (1 out of 4) for innovation in developing automated reporting tools and dashboards at Citi

* Academic Meritorious Award: Achieved 4th overall department rank in B.Tech Electronics and Communication Engineering, 2017-21 batch
