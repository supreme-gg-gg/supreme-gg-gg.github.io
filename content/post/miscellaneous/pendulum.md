---
title: Pendulum Tracking
subtitle: OpenCV for PHY180 Lab
date: 2024-09-28
tags: ["machine-learning", "cv"]
skills: ["Python", "OpenCV", "Matplotlib", "NumPy"]
---

Using OpenCV, I made my own script to track the motion of a pendulum in for my PHY180 (Mechanics) lab. The script detects the pendulum bob and track its motion in real-time for a directory of videos (samples taken) using `cv2`. The module supports:

1. Generating plots for amplitude vs time, period vs time, period vs length, etc.

2. Performing curve fitting using `scipy` with uncertainties and residuals.

3. Calculating quantities such as period and Q-factor.

{{< button url="https://github.com/supreme-gg-gg/pendulum-tracking" >}}My Source Code{{< /button >}}

<!--more-->

View the source code and `README.md` for more information on how to use the script. This page has not been fully written yet. Please check back later for updates.
