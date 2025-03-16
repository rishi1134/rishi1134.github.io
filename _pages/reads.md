---
layout: archive
title: ""
permalink: /padailikhaikaroiasyasbano/
author_profile: true
---

{% include base_path %}

A Catalog of my recent reads in one place so I (the forgetful me) can easily reference them later

Recent reads,
======
* M. Bigverdi et al., “Perception Tokens Enhance Visual Reasoning in Multimodal Language Models,” Dec. 08, 2024, arXiv: arXiv:2412.03548. doi: 10.48550/arXiv.2412.03548.

  Adding Depth estimation capability to VLMs to reason better. Distills depth tokens from a VAE trained on depth maps

* Z. Liu et al., “Region-Adaptive Sampling for Diffusion Transformers,” Feb. 14, 2025, arXiv: arXiv:2502.10389. doi: 10.48550/arXiv.2502.10389.

  Optimized sampling strategy to reduce redundant steps and focus on active regions. Works when temporal consistency in model's focus is observed. Easy to integrate with exising models. Only active tokens passed to DiT while reusing prev noise for inactive regions. 

* Z. Yue, J. Wang, and C. C. Loy, “ResShift: Efficient Diffusion Model for Image Super-resolution by Residual Shifting”.

  Another neat paper towards minimizing sampling steps. Prior is the guassian with LR as mean instead of pure noise. Shifts the residual. Latent space denoising.

* T. Mayet, P. Shamsolmoali, S. Bernard, E. Granger, R. Hérault, and C. Chatelain, “TD-Paint: Faster Diffusion Inpainting Through Time Aware Pixel Conditioning,” Oct. 11, 2024, arXiv: arXiv:2410.09306. doi: 10.48550/arXiv.2410.09306.

  Another one! Prior is the guassian with masked-LR as mean instead of pure noise. Known region free of noise. Noise and De-noise only the unknown regions at pixel level.

* S. Taner, Z. Wang, and C. Studer, “Cauchy-Schwarz Regularizers,” Mar. 07, 2025, arXiv: arXiv:2503.01639. doi: 10.48550/arXiv.2503.01639.

  In progress

* J. Zhu, X. Chen, K. He, Y. LeCun, and Z. Liu, “Transformers without Normalization,” Mar. 13, 2025, arXiv: arXiv:2503.10622. doi: 10.48550/arXiv.2503.10622.

  In Progress. Replaces LayerNorm based conditioning with Tanh like op. Intuition - Input/Output mapping produced by LayerNorm is S-shaped. 

* M. Jia et al., “Visual Prompt Tuning,” Jul. 20, 2022, arXiv: arXiv:2203.12119. doi: 10.48550/arXiv.2203.12119.

  Learnable prompts for Encoders. Shallow and Deep Tuning. PEFT.
