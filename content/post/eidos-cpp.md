---
title: Eidos
subtitle: Building a C++ Deep Learning Library from Scratch
date: 2024-12-31
tags: ["cpp", "machine-learning", "personal-projects"]
---

Eidos is a project for educational purpose to build an entire deep learning library from scratch in C++. Inspired by libtorch, PyTorch's C++ frontend, we implemented MLP, CNN, RNN using only Eigen for parallelized linear algebra. James Zheng and I started this project during my final exam month in 2024 and got me grinding it for a month alongside 6 major course finals. Install and try Eidos:

```bash
git clone https://github.com/supreme-gg-gg/Eidos
mkdir build && cd build
cmake .. && make
sudo make install
```

<!--more-->

The goal of the project is to understand the underlying concepts of simple deep learning models and how they work in order to build a solid foundation before moving ahead to convoluted ML concepts. We aim to provide a similar API interface to PyTorch and Keras for ease of use. We achieved similar performance with PyTorch on simple datasets such as MNIST, even though it takes longer to train (due to the lack of GPU support). _You can optionally setup `OpenMP` to achieve some sort of parallelism on CPU because it is supported by Eigen._

Here is an example of how to build a simple model using Eidos:

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

> This assumes that you have already loaded numerical or image data using our built-in data loader, such as `auto data = NumericDataLoader("mnist_train.csv", "label", label_map).train_test_split(0.8, 32);`.

The above code barely scratches the surface of what Eidos can do. Checkout our full documentation and examples on our GitHub repository.

The three biggest skills I learned from this project are:

- Object Oriented Programming in C++ (how to design a library)

- Eigen for linear algebra (finally it's not numpy anymore!)

- Deep Learning concepts (what's inside the black box??)

Sometimes, the best way to learn is to build something from scratch. Even though this likely isn't a library you would use in production, the knowledge gained from building it is invaluable. Furthermore, I am now 100x more grateful for the existence of PyTorch and TensorFlow after going through the ordeal of doing everything from scratch.

{{< button url="https://github.com/supreme-gg-gg/Eidos" >}}Learn more about Eidos!{{< /button >}}
