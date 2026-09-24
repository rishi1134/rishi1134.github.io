---
title: "Automatic Calibration of Tennis Court Images via Projective Invariants"
collection: talks
permalink: /kala/courtcalib
level: Industry
year: "2021"
category: core-cv
order: 2
header:
  teaser: /images/courtcalib_out.png
teaser: /images/courtcalib_out.png
tags: ["Classical Computer Vision", "Projective Geometry", "Homography", "Cross-Ratio Invariants"]
affiliation: "Computer Vision Intern | PlaEye LLC"
excerpt: "Single-view sports camera calibration algorithm exploiting projective invariants and cross-ratios to reliably estimate planar homographies under severe occlusion and missing court corner keypoints."
---

## Overview

Monocular camera calibration is fundamental for automated sports analytics, enabling player tracking, ball trajectory reconstruction, and metric coordinate mapping. However, broadcast camera feeds frequently suffer from severe occlusion caused by players, umpire stands, nets, or non-standard zoom levels where court corners lie entirely outside the field of view.

During my Computer Vision internship at PlaEye LLC, I designed a novel calibration framework that overcomes single-view feature degradation by exploiting projective geometric invariants.

*(Note: Proprietary commercial implementation details have been omitted; key mathematical formulations and empirical validation outputs are presented below.)*

---

## Problem Statement

Standard camera calibration relies on establishing point correspondences between image coordinates $(u, v)$ and canonical 3D/2D model points $(X, Y)$ to solve the planar homography matrix $H \in \mathbb{R}^{3 \times 3}$:

$$\begin{bmatrix} u \\ v \\ 1 \end{bmatrix} \sim H \begin{bmatrix} X \\ Y \\ 1 \end{bmatrix}$$

In extreme broadcast angles or tight zoom levels, the outer court boundary corners are occluded or clipped. Conventional Direct Linear Transformation (DLT) and RANSAC-based keypoint matching break down due to insufficient observable correspondences.

---

## Methodology: Projective Invariance & Cross-Ratios

To address degenerate keypoint visibility, we utilize the fundamental principle of the **Cross-Ratio** of four collinear points $(A, B, C, D)$:

$$\text{Cr}(A, B; C, D) = \frac{(x_A - x_C)(x_B - x_D)}{(x_B - x_C)(x_A - x_D)}$$

A central theorem of projective geometry states that the cross-ratio is **strictly invariant under perspective projection**:
$$\text{Cr}(A, B; C, D) = \text{Cr}(a, b; c, d)$$

By identifying collinear segment intersections on visible court markings (service lines, singles sidelines, center mark) and computing their invariant ratios against standard ITF court specifications:
1. We analytically recover virtual landmark points located in occluded or out-of-frame court regions.
2. The synthesized virtual landmarks provide sufficient non-collinear constraints to reliably solve for the 8 degrees-of-freedom homography matrix $H$.
3. Non-linear Levenberg-Marquardt refinement minimizes geometric reprojection error across all visible line segments.

---

## Calibration Workflow

![Court Calibration Pipeline Flowchart](../../images/courtcalib_flow.png)
*Figure 1: Procedural workflow for court boundary detection, cross-ratio landmark synthesis, and metric homography estimation.*

---

## Experimental Validation & Results

### 1. Canonical Court Calibration
In standard full-court views, the algorithm automatically extracts court line primitives, matches intersection candidates, and estimates the metric court plane with sub-pixel reprojection accuracy:

![Calibrated Tennis Court](../../images/courtcalib_out.png)
*Figure 2: Automated court calibration with estimated court boundaries highlighted in blue.*

### 2. Extreme Occlusion & Partial Field-of-View Recovery
When the camera view is severely cropped or occluded—a scenario where conventional feature-matching pipelines fail completely—the cross-ratio formulation accurately recovers the full court model:

![Occluded Court Calibration](../../images/courtcalib_out2.png)
*Figure 3: Calibration under extreme occlusion. Exploiting collinear cross-ratio invariance allows exact metric court estimation despite missing corners.*
