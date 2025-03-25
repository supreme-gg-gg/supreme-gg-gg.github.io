---
title: Trainify
subtitle: Watch your AI agent come to live!
date: 2025-03-23
tags: ["hackathon", "machine-learning", "cv", "full-stack", "genai"]
skills: ["GCP", "Docker", "Kubernetes", "Firebase", "Python", "PyTorch"]
---

Generate 3D environments from real world images and train reinforcement learning agents in the cloud with Trainify. Our platform, built on GCP, powered by agentic LLM, and natively integrated with core RL toolkits, simplifies the process of creating and training AI agents in 3D environments.

{{< gallery caption-effect="fade" >}}
{{< figure link="/img/trainify/cloud.png">}}
{{< figure link="/img/trainify/demo.png">}}
{{< figure link="/img/trainify/pipeline.png">}}
{{< /gallery >}}

<!--more-->

## Inspiration

We were inspired by the increasing need for realistic 3D environments in various fields such as robotics training, game development, and simulation.

For example, NVIDIA just showcased their robot Blue and a new framwork to train physical AI and robots in virtual environments. However, using their stack (Omniverse, Cosmos, and Issac Sim) is not accessible for beginners and those starting to learn RL.

Current solutions often require advanced technical skills and specialized knowledge. We wanted to democratize this process by leveraging the power of generative AI to make 3D environment creation accessible to everyone, regardless of their technical background.

## Features

> Imagine Google Colab (cloud collaboration and computing) + Cursor (agentic editor) + Blender/Unity (3D modelling) but specialized in reinforcement learning.

- Users can describe their desired environment using natural language prompts with their uploaded reference images for simplistic workflow

- Segment objects of interest using the text prompt and turn images into 3D object representation where you can explore and modify in real time

- Intuitive tools allow users to adjust object positions, properties, and relationships within the 3D space with our cloud-based collaborative editor

- Built-in reinforcement learning capabilities enable users to train AI agents to perform tasks within their custom environments

- An integrated Gemini-powered chatbot provides context-aware assistance during every step of the process.

Our cloud platform natively integrates all necessary RL toolkits like OpenAI Gym, PyBullet (physics engine), and Stable Baselines3 for seamless training and evaluation of AI agents.

{{< button url="https://devpost.com/software/trainify?ref_content=my-projects-tab&ref_feature=my_projects" >}}Checkout our devpost{{< /button >}}
