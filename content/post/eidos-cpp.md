---
title: Eidos
subtitle: Building a C++ Deep Learning Library from Scratch
date: 2024-12-31
tags: ["cpp", "machine-learning", "personal-projects"]
---

Eidos is a project for educational purpose to build an entire deep learning library from scratch in C++. It implemented MLP, CNN, RNN and helper utilities (e.g. data loader) using only Eigen for parallelized linear algebra. James Zheng and I started this project during my final exam month in 2024 and got me grinding it for a month alongside 6 major course finals.

The goal is to understand the underlying concepts of these models and how they work. The project is inspired by the libtorch, PyTorch's C++ frontend. We aim to provide a similar API interface to PyTorch and Keras for ease of use. We achieved similar performance with PyTorch on simple datasets such as MNIST, for example, to create a model:

```cpp
Model model;
model.Add(new DenseLayer(784, 128));
model.Add(new ReLU());
model.Add(new DenseLayer(128, 10));
```

We have also implemented other layers and activations like `Conv2D`, `MaxPool2D`, `GRU`, `BatchNorm`, etc. The model can be trained and tested using the following code:

```cpp
// Create optimizer and loss function
Adam optimizer(0.001);
CrossEntropyLoss loss_fn;

// Train and test the model using convenience API
model.Train(data.training.inputs, data.training.targets, 5, &optimizer, &loss_fn);
model.Test(data.testing.inputs, data.testing.targets, &loss_fn);

// Save the model
model.Serialize("myModel.bin");
```

{{< button url="https://github.com/supreme-gg-gg/Eidos" >}}Learn more about Eidos!{{< /button >}}
