---
layout: post
title:  "ComfyUI Weekly Update: Free Lunch and more."
categories: comfyui update
---

Here's what's new recently in [ComfyUI](https://github.com/comfyanonymous/ComfyUI).

[Here's the link to the previous update in case you missed it.]({{site.baseurl}}/comfyui/update/2023/09/17/Weekly-update.html)

## New Nodes

FreeU: An implementation of [FreeU: Free Lunch in Diffusion U-Net](https://github.com/ChenyangSi/FreeU). The node can be found in the _for_testing category. The default options on the node are the suggested settings for SD2.1. To decrease the chaos in the image/increase contrast increase b1 and b2 and decrease s1 and s2. b1/b2 have stronger effects than s1/s2. You should play around with the values and see what works the best for your favorite model and type of image.

LatentAdd, LatentSubtract and LatentMultiply: These new nodes can be found in latent->advanced. They can be used to add the values of two latents together, subtract them or multiply the values of a latent by a number. Interestingly it looks like multiplying a latent by -1 can be used to invert the colors of an image in latent space. I implemented them more for experimental reasons than practical reasons.

## Updates

Lora weights are now converted on the GPU when possible so they should apply faster.

ImageScale related nodes can now use lanczos.

Added support for controlnet models that are a different architecture from the base one.


## Some Cool ComfyUI related things 

[Dynamic Thresholding](https://github.com/mcmonkeyprojects/sd-dynamic-thresholding) now works on ComfyUI.

[CushyStudio](https://github.com/rvion/CushyStudio) an interesting frontend for ComfyUI that lets you code workflows is back in active development.

[ComfyUI is now on RunDiffusion](https://rundiffusion.com/comfyui-workflows), this is a paid service to run stable diffusion in the cloud but they seem to have put effort into supporting ComfyUI.

