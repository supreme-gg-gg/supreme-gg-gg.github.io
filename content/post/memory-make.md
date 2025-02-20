---
title: MemoryMake
subtitle: Turn single 2D photos into immersive, navigable 3D worlds
date: 2025-01-26
tags: ["full-stack", "hackathon", "machine-learning", "python"]
---

As memories pile up in our camera rolls or remain abstract ideas, we wanted to create a way to truly experience them. MemoryMake was born from the idea of transforming ordinary photos and text prompts into dynamic, navigable, and visually engaging 3D environments—so users can explore their cherished moments instead of merely scrolling past them.

Paul, Nelson, and I built Memory Make by taking the unconventional route, stepping away from common hackathon LLM apps and focusing on cutting edge computer vision research. We won the best social hacks at Queen's University's QHacks 2025.

{{< gallery caption-effect="fade" >}}
{{< figure link="/img/memory/temple.png">}}
{{< figure link="/img/memory/qhacks.JPG">}}
{{< figure link="/img/memory/pipe.png">}}
{{< /gallery >}}

<!--more-->

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

> They say a picture is worth a thousand words, but what about a 3D environment? 🤔
