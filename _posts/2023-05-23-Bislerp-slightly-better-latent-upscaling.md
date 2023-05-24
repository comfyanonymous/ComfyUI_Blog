---
layout: post
title:  "Bislerp: Slightly Better Latent Upscaling with Slerp"
categories: research
---

I noticed slerp was commonly used for interpolating between latents to make animations with Stable Diffusion. Since it seemed to work for latent interpolation I decided to try to apply it to scaling latents. It's bilinear but with slerp instead of linear so it's bislerp.

I know the math doesn't make that much sense but it seems to give some good results:

Here is a non cherry picked example with a simple "hiresfix" or 2 pass type workflow with a 2x upscale with nearest-exact, bislerp and bilinear in that order (if you want to see the exact workflows you can open these images in [ComfyUI](https://github.com/comfyanonymous/ComfyUI):

<p float="left">
  <img src="{{site.baseurl}}/assets/b_nearest_exact.png" width="100%" />
  <img src="{{site.baseurl}}/assets/b_bislerp.png" width="100%" /> 
  <img src="{{site.baseurl}}/assets/b_bilinear.png" width="100%" />
</p>

You'll notice that the image in the middle seems more alive. With bislerp the woman actually has some color in her and looks healthy. Bislerp is similar to bilinear but in my opinion produces better colors. From my testing it seems to produce consistently better results than the other simple latent upscaling methods.

For how to use this on [ComfyUI](https://github.com/comfyanonymous/ComfyUI), make sure you are updated to the latest ComfyUI (update/update_comfyui.bat on the standalone, make sure you update even if you have freshly downloaded the standalone) and "bislerp" will be a valid option on the "Upscale Latent" node. You can load the images in this post in ComfyUI to get a workflows.

For other interfaces my [currently very unoptimized function](https://github.com/comfyanonymous/ComfyUI/blob/c00bb1a0b78f0d2cf2e4ec2dd9ae7d61cb07a637/comfy/utils.py#L50) should be very easy to implement.

Try it out and let me know what you think.
