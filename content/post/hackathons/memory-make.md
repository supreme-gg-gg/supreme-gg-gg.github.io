---
title: MemoryMake
subtitle: Turn single 2D photos into immersive, navigable 3D worlds
date: 2025-01-26
tags: ["full-stack", "hackathon", "machine-learning", "python"]
skills: ["Python", "FastAPI", "React", "PyTorch", "Tensorflow"]
---

As memories pile up in our camera rolls or remain abstract ideas, we wanted to create a way to truly experience them. MemoryMake was born from the idea of transforming ordinary photos and text prompts into dynamic, navigable, and visually engaging 3D environments—so users can explore their cherished moments instead of merely scrolling past them.

Paul, Nelson, and I built Memory Make by taking the unconventional route, stepping away from common hackathon LLM apps and focusing on cutting edge computer vision research. We won the best social hacks at Queen's University's QHacks 2025.

{{< gallery caption-effect="fade" >}}
{{< figure link="/img/memory/temple.png">}}
{{< figure link="/img/memory/qhacks.JPG">}}
{{< figure link="/img/memory/pipe.png">}}
{{< /gallery >}}

<!--more-->

I am sorry to disappoint, but you are not finding another ChatGPT wrapper here. Instead, we are reimagining how you can interact with your memories. MemoryMake is a full-stack application that transforms single 2D photos into immersive, navigable 3D worlds.

> They say a picture is worth a thousand words, but what about a 3D reconstruction? 🤔

We were inspired to build memory make by latest advancements in computer vision such as neural radiance fields (NeRF) and 3D gaussian splatting (3DGS). To limit the scope of the project in the duration of a hackathon, we chose to reconstruct only a 180 degree panoramic view intead of generating entire virtual worlds.

The way we we designed MemoryMake is to take in either 2D photos, extract depth information just like how your eyes perceive depth in the real world, and then apply the depth information and other 3D transformations to reconstruct a 3D model to give users the experience of walking through their memories. The benefits of this pipeline is that we can easily integrate with existing robust 2D vision tools such as neural style transfer and cycle GAN to apply unique artistic styles or make modifications to the image or generate creative images from text prompts using generative models.

At the end, we utilize three.js to render the 3D model in the browser and allow users to navigate through their memories.

## Demo

For a comprehensive showcase of the features, instead of listing them out, allow me to redirect you to our [Youtube Demo Video](https://youtu.be/Lyfvt5-SsFA).

## Tech Stack

- **MiDaS**: Monocular depth estimation developed by Intel Labs.

- **Open3D**: Python library for 3D data processing, used for point cloud generation, surface reconstruction, meshing, visualization, and more.

- **Neural Style Transfer**: Allows us to apply the art style of one image to the content of another image.

- **Stable Diffusion**: Open source text to image generation allows for text to 3D conversion.

- **Frontend**: React, Three.js

- **Backend**: FastAPI

Please visit our [Devpost](https://devpost.com/software/memorymake) for more details on our project. Check out our GitHub for the codebase and more information.

{{< button url="https://github.com/nelonmelons/memorymake" >}}GitHub{{< /button >}}
