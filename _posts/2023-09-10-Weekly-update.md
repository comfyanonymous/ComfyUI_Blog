---
layout: post
title:  "ComfyUI Weekly Update: DAT upscale model support and more T2I adapters."
categories: comfyui update
---

Here's what's new recently in [ComfyUI](https://github.com/comfyanonymous/ComfyUI).

[Here's the link to the previous update in case you missed it.](/ComfyUI_Blog/comfyui/update/2023/09/02/Weekly-update.html)

### New upscale model supported: DAT

[DAT](https://github.com/zhengchen1999/DAT) is a recent upscale model architecture that seems to give pretty decent results. That link contains a link to download some pretrained model files if you want to give it a try.

Upscale models can be used [like this](https://comfyanonymous.github.io/ComfyUI_examples/upscale_models/) in ComfyUI.

ComfyUI borrows [code from chaiNNer](https://github.com/chaiNNer-org/chaiNNer/tree/main/backend/src/nodes/impl/pytorch/architecture) for the upscale models so thanks to their great work ComfyUI supports almost all the models that they support. Some interesting upscale models to try that you may be less familiar with are [HAT](https://github.com/XPixelGroup/HAT#how-to-test) and [Omni-SR](https://github.com/Francis0625/Omni-SR#preparation).


### Support for T2I adapters in diffusers format

TencentARC and HuggingFace released [these T2I adapter model files.](https://huggingface.co/collections/TencentARC/t2i-adapter-sdxl-64fac9cbf393f30370eeb02f) ComfyUI has been updated to support this file format. As a reminder T2I adapters are used exactly like [ControlNets in ComfyUI](https://comfyanonymous.github.io/ComfyUI_examples/controlnet/). T2I adapters take much less processing power than controlnets but might give worse results.

### New nodes

Conditioning (Set Area with Percentage): Set prompt areas for [Area Composition](https://comfyanonymous.github.io/ComfyUI_examples/area_composition/) with coordinates and sizes with values 0.0 to 1.0 instead of pixel values.

### UI changes

You can now paste (CTRL-V) images onto the canvas and it will automatically create a LoadImage node. You can also paste (CTRL-V) images to a selected Load Image node.

Less trailing zeros are now shown in the UI.

Cancelling a generation now works in every progress bar.

### Notable Bug fixes

If you run a publicly accessible instance of ComfyUI which I don't really recommend in the first place please update it to the latest version because a [security bug was fixed](https://github.com/comfyanonymous/ComfyUI/commit/d6d1a8998fa60da9265ea3e9db35d80441cac6fd). 

This does not affect regular local installs so if you use the standalone windows download for example this does not affect you at all.


Big thanks to the one who found and reported the issue.


### Some Cool custom nodes

[ControlNet-LLLite](https://github.com/kohya-ss/ControlNet-LLLite-ComfyUI): nodes to use [controlnet-lllite models](https://huggingface.co/kohya-ss/controlnet-lllite/tree/main)

[ComfyUI Translation](https://github.com/AIGODLIKE/AIGODLIKE-ComfyUI-Translation): Translating ComfyUI to different languages like Chinese, Japanese and others.

