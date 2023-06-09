---
title: UnityMLStableDiffusion
date: 2023-03-29T12:17:58+08:00
draft: False
featuredImage: https://wallpaperhub.app/api/v1/get/11953/0/1080p
featuredImagePreview: https://wallpaperhub.app/api/v1/get/11953/0/1080p
---

# [keijiro/UnityMLStableDiffusion](https://github.com/keijiro/UnityMLStableDiffusion)

Unity Core ML Stable Diffusion Plugin
=====================================

Stable Diffusion plugin for Unity, based on [Apple's Core ML port]. You can run
the model on-editor and at-runtime without needing any extra components.

[Apple's Core ML port]: https://github.com/apple/ml-stable-diffusion

System Requirements
-------------------

- Unity 2023.1 or later
- Apple Silicon Mac (editor/runtime support) with macOS 13.1 or later
- iPad Pro with Apple silicon (runtime support) with iOS 16.2 or later

Although the plugin supports iOS, it requires huge amount of memory to run the
model, so it only supports memory-rich iPad models.

How To Try
----------

Before running the sample project, you must put the model files in the
`Assets/StreamingAssets` directory.

- Clone or download the [pre-converted Stable Diffusion 2 model repository].
- Copy the `split_einsum/compiled` directory into `Assets/StreamingAssets`.
- Rename the directory to `StableDiffusion`.

[pre-converted Stable Diffusion 2 model repository]:
  https://huggingface.co/apple/coreml-stable-diffusion-2-base

It takes a long time (a few minutes) for the first run. After this
initialization step, it only takes a few tens of seconds to generate an image.
