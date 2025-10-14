---
title: Home
layout: home
nav_order: 1
permalink: /
---

# Create stunning 3D worlds.
{: .fs-9 }

PowerImaginator brings your ideas from text to (virtual) reality in immersive, infinitely explorable 3D environments.
{: .fs-6 .fw-300 }

[Get started now](getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

<video src="assets/video/demo.mp4" controls playsinline muted preload="metadata" style="width: 100%"></video>

PowerImaginator is still an early-stage research prototype. Expect broken and low-quality output. We are working continuously to improve PowerImaginator until it is a state-of-the-art 3D scene generation system.
{: .warning }

The quickest way to improve quality is likely modifying the [PowerImaginator server](https://github.com/PowerImaginator/powerimaginatorserver/blob/main/main_module/main.py) to use different inpainting and depth estimation models. To keep iteration times manageable during development, we currently use a model based on Stable Diffusion 1.5. Upgrading to a more recent model (e.g. Flux Fill) would double resolution and generate more coherent images. If you generate anything impressive, please tell us about it on our [Discord server](https://discord.gg/Vk3Wh5ZQYD)!
{: .note }

## Already have an API token?

If you already received a Server URL and API Token from someone else, just follow the [client setup instructions](getting-started#install-the-client-app).
