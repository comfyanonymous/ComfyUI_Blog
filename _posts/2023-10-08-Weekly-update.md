---
layout: post
title:  "ComfyUI Weekly Update: Pytorch 2.1, New Sampler nodes, Primitive node improvements."
categories: comfyui update
---

Here's what's new recently in [ComfyUI](https://github.com/comfyanonymous/ComfyUI).

[Here's the link to the previous update in case you missed it.]({{site.baseurl}}/comfyui/update/2023/09/24/Weekly-update.html)

## Standalone Windows Package Updates

The [standalone windows package](https://github.com/comfyanonymous/ComfyUI/releases) now uses python 3.11 with pytorch 2.1 cu121. Xformers has been removed. If you want to update to it you have to download a new version of the standalone. On my 3090 TI I get a 5-10% performance increase versus the old standalone.

If you are happy with python 3.10 and pytorch cu118 with xformers you can continue using the update scripts in the update folder on the old standalone to keep ComfyUI up to date.

To migrate from one standalone to another you can move the ComfyUI\models, ComfyUI\custom_nodes and ComfyUI\extra_model_paths.yaml (if you have one) to your new standalone.

## Primitive Node Improvements

Primitive nodes can now be connected to different inputs even when the type does not match exactly. As a reminder the easiest way to use primitive nodes you can right click node -> convert to input -> double click on the new input.

Since this is a major rework of how Primitive nodes work it seems to have broken some custom scripts so if you get errors make sure you update everything and if that doesn't fix it try disabling any custom scripts that are erroring out. You can see script errors by looking in your browser console or in settings->View Logs.

## New Nodes

### SamplerCustom

This node and all the related ones can be found in sampling->custom_sampling. With this node it is now possible for samplers and schedulers to be their own node. This makes it much easier for people to write their own schedulers or samplers because they can now be written as standalone nodes. It also makes it easier to expose advanced options that are specific to a single sampler or scheduler by making a node for that specific sampler with those options exposed.

There are new nodes like KarrasScheduler and SamplerDPMPP_SDE, these are examples of nodes that implement a single scheduler or sampler and expose some advanced options.

The SamplerCustom has two different latent outputs: output and denoised_output, those correspond to the "return_with_leftover_noise" option on the advanced sampler.

Here is the basic way of using the SamplerCustom node:

<p float="left">
  <img src="{{site.baseurl}}/assets/custom_sampler.png" width="100%" />
</p>


### Others

PorterDuffImageComposite: Porter-Duff Image Composite node.

SplitImageWithAlpha, JoinImageWithAlpha: nodes to add and remove an alpha channel from an image. Can be useful if you want to save an image with an alpha channel.

## Other Updates

The mask nodes have been updated to handle batches of masks which makes them useful for animations.

LatentUpscale and ImageScale now accept a width or height of zero if you want to scale images proportionally.


## Some Cool ComfyUI Related Projects

[AnimateDiff For ComfyUI](https://github.com/Kosinkadink/ComfyUI-AnimateDiff-Evolved) and the related [Prompt Scheduling Nodes](https://github.com/FizzleDorf/ComfyUI_FizzNodes) now support SDXL.

[A better IPAdapter implementation for ComfyUI](https://github.com/cubiq/ComfyUI_IPAdapter_plus), watch the [Youtube Video](https://www.youtube.com/watch?v=7m9ZZFU3HWo) for a detailed view of it.
