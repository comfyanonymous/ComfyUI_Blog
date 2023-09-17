---
layout: post
title:  "ComfyUI Weekly Update: New Model Merging nodes."
categories: comfyui update
---

Here's what's new recently in [ComfyUI](https://github.com/comfyanonymous/ComfyUI).

[Here's the link to the previous update in case you missed it.](/ComfyUI_Blog/comfyui/update/2023/09/10/Weekly-update.html)

Not many new features this week but I'm working on a few things that are not yet ready for release.

### Model Merging

There are two new model merging nodes:

ModelSubtract: `(model1 - model2) * multiplier`

ModelAdd: `model1 + model2`

They can be used to replicate the "add difference" model merging function present in other UIs.

As a reminder Models can be merged on the fly in ComfyUI in an extremely efficient way. [See this page for some examples including one with the new nodes.](https://comfyanonymous.github.io/ComfyUI_examples/model_merging/)

### New Sampler: DDPM

Gives outputs that are extremely close to euler_ancestral.

### Some Cool new ComfyUI related projects 

[A simple prompt generator for ComfyUI utilizing ExLlama](https://github.com/Zuellni/ComfyUI-ExLlama-Nodes)

[New Krita plugin that uses ComfyUI](https://github.com/Acly/krita-ai-diffusion)
