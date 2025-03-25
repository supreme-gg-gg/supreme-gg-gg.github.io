---
title: NeuroSteady 
subtitle: Wearable tech for hand tremor stabalization in neurosurgery
date: 2025-02-20
tags: ["machine-learning", "hackathon", "hardware"]
skills: ["ArduinoIDE", "cpp", "PyTorch", "NumPy", "Python"]
---

In the 24-hour BMEC hackathon, we used few-shot transfer learning with CNN-LSTM to detect slight hand tremors of neurosurgeons during surgery, ensembled with a simple majority voting system with a sliding window time-frequency analysis. This triggers an intervention using a wearable device consistent of servo actuators to stabalize the hand of the surgeon during operation.

{{< gallery caption-effect="fade" >}}
{{< figure link="/img/neurohacks/wear.jpeg">}}
{{< figure link="/img/neurohacks/device.jpeg">}}
{{< figure link="/img/neurohacks/team.jpeg">}}
{{< /gallery >}}

<!--more-->

Hand tremors are a common problem in neurosurgery, where even minor tremors can have a significant impact on the outcome of the surgery. This is natural and can be caused by stress, fatigue, or other factors. The current solutions are either too expensive (such as da Vinci robot) or not effective enough and some surgery must be done by hand. Portability and intuitiveness of use is also a need of stakeholders. **The goal of this project is to provide a cost-effective solution that can be used in real-time during surgery.**

## The Solution

We trained a CNN-LSTM model from scratch on a public Parkinson's hand tremor dataset and fine tuned it using our own accelerometer recordings. The model achieved over 90% accuracy in the base dataset and 85% accuracy in our own dataset. We then used a simple majority voting system with a sliding window time-frequency analysis to detect tremors in real-time. The wearable device applies a counteracting force to the hand to stabilize it during surgery.

The design process, from the initial idea to the final prototype, was recorded throughly in our GitHub.

> Check out our GitHub and like our project it's really cool!!!

{{< button url="https://github.com/supreme-gg-gg/NeuroSteady/tree/main" >}}Checkout our devpost{{< /button >}}
