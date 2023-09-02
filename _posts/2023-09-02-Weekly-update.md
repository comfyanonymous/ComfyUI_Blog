---
layout: post
title:  "ComfyUI Weekly Update: Faster VAE, Speed increases, Early inpaint models and more."
categories: comfyui update
---

Here's what's new recently in [ComfyUI](https://github.com/comfyanonymous/ComfyUI).

[Here's the link to the previous update in case you missed it.](/ComfyUI_Blog/comfyui/update/2023/08/27/Weekly-update.html)

Along with the regular bug fixes what's new is:

### Faster VAE on Nvidia 3000 series and up

The VAE is now run in bfloat16 by default on Nvidia 3000 series and up. This should reduce memory and improve speed for the VAE on these cards. People using other GPUs that don't natively support bfloat16 can run ComfyUI with `--fp16-vae` to get a similar speedup by running the VAE in float16 however this isn't the default because it can cause black images due to the values in the VAE overflowing (bfloat16 doesn't have that issue) which is why the default for other cards is full precision float32.

### Speed increases

The CLIPVision model is now run on the GPU unless you have a low vram system which should speed up ReVision and other workflows that depend on it. The Canny preprocessor node is now also run on the GPU so it should be fast now.

### Support for SDXL inpaint models

Huggingface has released an early [inpaint model based on SDXL](https://huggingface.co/diffusers/stable-diffusion-xl-1.0-inpainting-0.1). It is in huggingface format so to use it in ComfyUI, download [this file](https://huggingface.co/diffusers/stable-diffusion-xl-1.0-inpainting-0.1/blob/main/unet/diffusion_pytorch_model.fp16.safetensors) and put it in the ComfyUI/models/unet directory. Then you can use the advanced->loaders->UNETLoader node to load it.

[Here's an example workflow](https://gist.github.com/comfyanonymous/6792ae5460c2cadb16d4bd60381c7e06). Note that I renamed diffusion_pytorch_model.fp16.safetensors to diffusers_sdxl_inpaint_0.1.safetensors to make things more clear.

Note that in ComfyUI you can right click the Load image node and "Open in Mask Editor" to add or edit the mask for inpainting. You can also copy images from the save image to the load image node by right clicking the save image node and "Copy (clipspace)" and then right clicking the load image node and "Paste (clipspace)".

### UI changes

Groups can now be used to mute or bypass multiple nodes at a time. [See the pull request for more information](https://github.com/comfyanonymous/ComfyUI/pull/1358). As a reminder bypassing a node (CTRL-B or right click->bypass) can be used to disable a node while keeping connections though the node intact.

The middle mouse button can now be used to drag the canvas.

The history is now displayed in reverse order to make it more easy to load the last processed workflows.

### Node changes

New Node: mask->ImageColorToMask: convert a specific color in an image to a mask.

VAEDecodeTiled and VAEEncodeTiled: you can now set the tile size.

### For custom node developers

If your custom node broke this week it's probably because of [this commit](https://github.com/comfyanonymous/ComfyUI/commit/1c012d69afa8bd92a007a3e468e2a1f874365d39)

### Some Cool recent custom nodes

[FABRIC for ComfyUI](https://github.com/ssitu/ComfyUI_fabric)

[AnimateDiff for ComfyUI with ControlNet](https://github.com/Kosinkadink/ComfyUI-AnimateDiff/)

