---
layout: post
title:  "ComfyUI is now 4 months old!"
date:   2023-05-18 20:00:00 +0100
categories: comfyui update
---

The original goal of [ComfyUI](https://github.com/comfyanonymous/ComfyUI) was to create a powerful and flexible stable diffusion backend/interface. I think it's going pretty well.

The reason I started writing ComfyUI is that I got a bit too addicted to generating images with Stable Diffusion. The other tools available started lacking the flexibility and power that I desired. I also wanted to learn the core functions of Stable Diffusion and how it works. I wanted to do better than everyone else especially in terms of software design. ComfyUI is far from perfect, but I feel it has matured over the months and is more stable and bug free than others.

![ComfyUI screenshot]({{site.baseurl}}/assets/comfyui.png)

In only 4 months, thanks to everyone who has contributed, ComfyUI grew into an amazing piece of software that in many ways surpasses other stable diffusion graphical interfaces: in flexibility, base features, overall stability, and power it gives users to control the diffusion pipeline.

It is also by far the easiest stable interface to install. If you have a nvidia card on windows all you have to do is download the [portable build on this page and read the very short instructions.](https://github.com/comfyanonymous/ComfyUI#installing)

Then for information how to use it you can take a look at the [examples page](https://comfyanonymous.github.io/ComfyUI_examples/)

I often see some questions about what ComfyUI has over most other UIs:

- Saving your entire workflow is easy: The entire workflow is saved to every image you generate. This makes loading past workflows and sharing them super easy.

- A real queue system built into the backend. Queue any combinations of workflows you want, go do something else and come back to all your generated images.

- Important things like ControlNet and support for all the LoRa/Locon/LoHa/Lycoris/LoKr flavors are a core feature.

- Much higher performance out of the box on most systems. Some easy to use [standalone packages with nightly pytorch for windows](https://github.com/comfyanonymous/ComfyUI/releases) for those who want to get max performance with the latest bleeding edge python3.11 + nightly pytorch2.1 cu121.

- Writing custom nodes is extremely easy and they are automatically accessible through the api.

- Supports a few things not implemented in other SD interfaces like [Noisy Latent Composition](https://comfyanonymous.github.io/ComfyUI_examples/noisy_latent_composition/), [GLiGEN](https://comfyanonymous.github.io/ComfyUI_examples/gligen/) and proper [unCLIP model](https://comfyanonymous.github.io/ComfyUI_examples/unclip/) support (supports using multiple images as input).


There is still a lot to do especially when it comes to overall user experience and documentation but I think that the future is Comfy.

My vision for the future is to keep ComfyUI updated with all the cool new things that come out, improve performance and make the software better. I and others in the ComfyUI community also have a few ideas of our own for some things that could improve Stable Diffusion for everyone so stay tuned.

## Third Party Resources

To show off the ComfyUI community here's a list of some third party resources, alternative frontends and extensions.


### Information and workflows

A lot of various information/workflows/etc...
<https://github.com/wyrde/wyrde-comfyui-workflows>

A list of Custom Nodes, Extensions, and Tools for ComfyUI
<https://github.com/WASasquatch/comfyui-plugins>

Node Guide (under construction at the time of writing)
<https://blenderneko.github.io/ComfyUI-docs/>

### Alternative Frontends

In ComfyUI the backend and frontend are decoupled from each other which makes writing an alternative frontend relatively easy.  ComfyUI is designed so backend extensions/custom nodes work with other frontends without issues. 

CushyStudio (control ComfyUI in visual studio code): <https://github.com/rvion/CushyStudio>

ComfyBox (A more standard user interface): <https://github.com/space-nuko/ComfyBox>

Integration for Blender: <https://github.com/AIGODLIKE/ComfyUI-BlenderAI-node>

ComfyUI serves as the backend for the Stable Horde: <https://github.com/Haidra-Org/hordelib>

Not really an alternative frontend but an extension to embed ComfyUI in the A1111 interface: <https://github.com/ModelSurge/sd-webui-comfyui>


### Custom nodes/extensions

ComfyUI is very extensible. If you want to explore the ecosystem, here are some repos that contain nodes/extensions.

* Most of these repos have more than one custom node. 
* Keep in mind some are WIP.

Extensive node suite with 100+ nodes for advanced workflows: 
<https://github.com/WASasquatch/was-node-suite-comfyui>

Cutoff implementation: 
<https://github.com/BlenderNeko/ComfyUI_Cutoff>

Tiled sampling (also called multidiffusion): 
<https://github.com/BlenderNeko/ComfyUI_TiledKSampler>

Different implementations of how to do prompt weighting: 
<https://github.com/BlenderNeko/ComfyUI_ADV_CLIP_emb>

Unsampling and other noise related tricks: 
<https://github.com/BlenderNeko/ComfyUI_Noise>

Making the "conditioning set area" less of a pain to use: 
<https://github.com/Davemane42/ComfyUI_Dave_CustomNode>

Conveniently enhance images through Detector, Detailer, Upscaler, Pipe, and more: 
<https://github.com/ltdrdata/ComfyUI-Impact-Pack>

WIP custom node manager: 
<https://github.com/ltdrdata/ComfyUI-Manager>

DeepFloyd IF in ComfyUI: 
<https://github.com/Zuellni/ComfyUI-Custom-Nodes>

<https://github.com/pythongosssss/ComfyUI-Custom-Scripts>

<https://github.com/xXAdonesXx/NodeGPT>

<https://github.com/Derfuu/Derfuu_ComfyUI_ModdedNodes>

<https://github.com/LucianoCirino/efficiency-nodes-comfyui>

<https://github.com/lilly1987/ComfyUI_node_Lilly>

<https://github.com/hnmr293/ComfyUI-nodes-hnmr>

<https://github.com/diontimmer/ComfyUI-Vextra-Nodes>

<https://github.com/diontimmer/Sample-Diffusion-ComfyUI-Extension>

<https://github.com/omar92/ComfyUI-QualityOfLifeSuit_Omar92>

<https://github.com/Fannovel16/FN16-ComfyUI-nodes>

<https://github.com/BadCafeCode/masquerade-nodes-comfyui>

<https://github.com/EllangoK/ComfyUI-post-processing-nodes>

<https://github.com/LEv145/images-grid-comfy-plugin>

<https://github.com/biegert/ComfyUI-CLIPSeg>

<https://github.com/m957ymj75urz/ComfyUI-Custom-Nodes>

<https://github.com/Jcd1230/rembg-comfyui-node>

<https://github.com/TinyTerra/ComfyUI_tinyterraNodes>

<https://github.com/diffus3/ComfyUI-extensions>

<https://github.com/guoyk93/yk-node-suite-comfyui>

<https://github.com/comfyanonymous/ComfyUI_experiments>

<https://github.com/gamert/ComfyUI_tagger>

<https://github.com/bmad4ever/ComfyUI-Bmad-Custom-Nodes>

<https://github.com/YinBailiang/MergeBlockWeighted_fo_ComfyUI>

<https://github.com/Kaharos94/ComfyUI-Saveaswebp>

<https://github.com/trojblue/trNodes>

<https://github.com/city96/ComfyUI_NetDist>

<https://github.com/SLAPaper/ComfyUI-Image-Selector>

<https://github.com/strimmlarn/ComfyUI-Strimmlarns-Aesthetic-Score>

<https://github.com/ssitu/ComfyUI_UltimateSDUpscale>

<https://github.com/space-nuko/ComfyUI-Disco-Diffusion>

<https://github.com/Bikecicle/ComfyUI-Waveform-Extensions>

<https://github.com/AlekPet/ComfyUI_Custom_Nodes_AlekPet>

<https://github.com/rock-land/graphNavigator>


Civitai also has some: <https://civitai.com/?query=comfyui>
