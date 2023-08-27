---
layout: post
title:  "ComfyUI Weekly Update: Better memory management, Control Loras, ReVision and T2I adapters for SDXL"
categories: comfyui update
---

I have decided to start posting weekly updates of what is new in ComfyUI.

Here's what's new recently in [ComfyUI](https://github.com/comfyanonymous/ComfyUI):

### Better Memory Management

ComfyUI will now try to keep weights in vram when possible. The default behavior before was to aggressively move things out of vram. This should make it use less regular ram and speed up overall gen times a bit. It makes it work better on free colab, computers with only 16GB ram and computers with high end GPUs with a lot of vram.

Because of this improvement on my 3090 TI the generation times for the default ComfyUI workflow (512x512 batch size 1, 20 steps euler SD1.5) with the default ComfyUI settings went from 1.38 seconds to 1.03 seconds.

### Control Loras

In case you missed it stability.ai released [Control Loras](https://huggingface.co/stabilityai/control-lora) for SDXL. In ComfyUI these are used exactly like [ControlNets](https://comfyanonymous.github.io/ComfyUI_examples/controlnet/)

### T2I adapters for SDXL

TencentARC released their [T2I adapters for SDXL](https://huggingface.co/TencentARC/T2I-Adapter/tree/main/models_XL). These are also used exactly like ControlNets in ComfyUI. T2I adapters are faster and more efficient than controlnets but might give lower quality. You should definitively try them out if you care about generation speed.

### ReVision

ReVision is high level concept mixing that only works on SDXL models. You can find workflows for it on the [SDXL examples page](https://comfyanonymous.github.io/ComfyUI_examples/sdxl/#revision)


### Some Cool Recent custom nodes (available in the [ComfyUI manager](https://github.com/ltdrdata/ComfyUI-Manager))

[IP adapter implementation for ComfyUI](https://github.com/laksjdjf/IPAdapter-ComfyUI): [IP adapter](https://github.com/tencent-ailab/IP-Adapter) for ComfyUI.

[Neural network latent upscale](https://github.com/Ttl/ComfyUi_NNLatentUpscale): Better way of upscaling latents.

