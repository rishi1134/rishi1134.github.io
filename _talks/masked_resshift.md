---
title: "Masked-ResShift: Pixel-Level Residual Shift for Image Inpainting"
collection: talks
permalink: /talks/masked
level: Graduate
year: "2024"
category: core-cv
order: 1
header:
  teaser: /images/masked_resshift_teaser.png
teaser: /images/masked_resshift_teaser.png
tags: ["Diffusion Models", "Image Inpainting", "Generative Vision", "Markov Process"]
affiliation: "Graduate Research (Deep Learning) | University at Buffalo"
codeurl: "https://github.com/rishi1134/masked-resshift"
paperurl: "/files/dl_report.pdf"
excerpt: "Investigates diffusion sampling efficiency for image inpainting by reformulating the reverse diffusion process with Masked-Variance Diffusion (MVD) and Exact Masked-Markov Diffusion (EMMD), cutting inference steps while preserving boundary fidelity."
---

## Overview

Diffusion models achieve state-of-the-art visual fidelity in image restoration and inpainting tasks. However, iterative denoising over the entire canvas introduces significant computational latency, especially when synthesizing only masked or missing regions. 

In this work, we investigate and formulate optimization strategies designed to accelerate inference in residual-shift diffusion frameworks (ResShift) without degrading restoration quality. We propose and evaluate two novel formulations: **Masked-Variance Diffusion (MVD)** and **Exact Masked-Markov Diffusion (EMMD)**.

- **Source Code & Models**: [GitHub Repository](https://github.com/rishi1134/masked-resshift)
- **Model Checkpoints**: [Trained Weights (Box)](https://buffalo.box.com/s/5mubxvt18kjl9q0mhjddazv0uishtsgu)
- **Full Research Report**: [Download PDF (4.1 MB)]({{ site.baseurl }}/files/dl_report.pdf)

---

## Technical Approach & Formulation

### 1. Masked-Variance Diffusion (MVD)
In conventional diffusion inpainting, Gaussian noise is injected uniformly across all pixels during the forward process. In MVD, we constrain the stochastic perturbation strictly to the unobserved/corrupted regions $\Omega_m$, while leaving the observed context $\Omega_{\\text{obs}}$ unperturbed:
- Prevents drift and distribution shifts in known image content.
- Anchors the reverse denoising trajectory directly to true boundary textures.
- Stabilizes early-step sampling, allowing larger step sizes with reduced iterations.

### 2. Exact Masked-Markov Diffusion (EMMD)
To address non-Markovian boundary artifacts in spatial masking, EMMD explicitly defines a true pixel-wise Markov forward process. By deriving the exact analytical posterior:
$$q(x_{t-1} \mid x_t, x_0, m)$$
conditioned on the binary spatial mask $m$, the reverse transitions adhere strictly to the true data distribution without heuristic boundary blending.

---

## Qualitative & Comparative Results

Below is a visual comparison between the baseline ResShift model and our proposed masked diffusion approach across diverse masking patterns:

![Masked-ResShift Qualitative Inpainting Comparison](../../images/masked_resshift_teaser.png)
*Figure: Qualitative comparison of inpainted regions across benchmark images. Our masked formulation maintains crisp structural boundaries and color consistency with significantly fewer reverse steps.*

---

## Full Research Report

<iframe src="{{ site.baseurl }}/files/dl_report.pdf"
        width="100%"
        height="850px"
        style="border: 1px solid #e2e8f0; border-radius: 6px;"
        title="Masked-ResShift Research Report">
    This browser does not support embedded PDFs. Please download the PDF to view it:
    <a href="{{ site.baseurl }}/files/dl_report.pdf" target="_blank">Download Research Report (PDF)</a>.
</iframe>
