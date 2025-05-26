---
title: "Masked-ResShift: Pixel-Level Residual Shift for Image Inpainting"
collection: talks
permalink: /talks/masked
order: 1
---

This project explores and tries to enhance the efficiency of diffusion-based image inpainting. #DDPM #ImageGeneration


We explore various optimization strategies aimed at accelerating the inference process without substantially compromising the quality of the result images. Our efforts build upon the existing frameworks, such as ResShift known for its efficiency in image restoration tasks and seek to refine these approaches further. This project implements two distinct strategies, including Masked-Variance Diffusion (MVD), where diffusion noise is primarily applied to unknown image regions, and Exact Masked-Markov Diffusion (EMMD), which defines a true pixel-wise Markov forward process with an exact posterior to guide the reverse diffusion. We examine and implement these techniques, from modifying network architectures to rethinking the diffusion process itself, all with the final goal of achieving faster, yet still effective, image inpainting.

[Our code and model is available here](https://github.com/rishi1134/masked-resshift)

<iframe src="{{ site.baseurl }}/files/dl_report.pdf"
        width="100%"
        height="800px"
        style="border: none;"
        title="Paper">
    This browser does not support PDFs. Please download the PDF to view it:
    <a href="{{ site.baseurl }}/files/dl_report.pdf" target="_blank">Download PDF</a>.
</iframe>
