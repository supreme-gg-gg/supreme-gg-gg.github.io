---
title: Block ML
subtitle: Drag and drop neural network builder like Scratch
date: 2024-08-25
tags: ["full-stack", "hackathon", "machine-learning"]
skills: ["JavaScript", "Node", "Express", "Keras"]
---

Most programmers were introduced to coding through Scratch, a block-based programming language that simplifies the process of buliding games, animations, and stories. Why not make machine learning as easy as Scratch, or even better -- directly with the framework that made Scratch? (IgnitionHacks)

{{< figure src="/img/block/demo.png" alt="Scratch-like editor" width="70%">}}

<!--more-->

Machine Learning shouldn't be limited to experienced software engineers, computer science majors, or other elites. It should be accessible to everyone, regardless of their background or knowledge in CS.

Our goal is to empower individuals to design, build, and deploy ML models, enabling them to solve problems with creativity and innovation. This project is a prototype web app that caters to both researchers and business professionals seeking quick, low-cost ML solutions, and students eager to explore AI through a Scratch-like block programming interface.

## Features

1. Drag and drop blocks to build powerful neural networks: built in functionalities to load and process data, highly customizable

2. Export generated Jupyter Notebook: easily download the notebook for further customization and deployment, work on Colab directly with Keras and TensorFlow

3. Train and predict: make predictions immediately after training, export and load trained models for future use

4. Visualize: Learn how neural networks work intuitively by building the piepiline and seeing live code generation

## Technologies

| Technology       | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| Google Blockly   | Framework for building block-based programming interfaces                   |
| Keras            | High-level neural networks API, written in Python and capable of running on top of TensorFlow |
| Express.js       | Web application framework for Node.js, used for building the backend server  |
| Webpack          | Module bundler for JavaScript applications, used for bundling the frontend code |

The key part of the project is to generate Python code from the blocks. Google Blockly help us to do this by using an abstract syntax tree (AST) to represent the blocks and then generate Python code from the AST. [Learn more about Blockly here](https://developers.google.com/blockly?_gl=1*11l5zs*_up*MQ..*_ga*MTMwNzgxNzM3MC4xNzM2NzkwODY4*_ga_R5G2Y6GLVC*MTczNjc5MDg2Ny4xLjEuMTczNjc5MDg3Ny4wLjAuMA..). _If you are using this for a hackathon too, their tutorials are high valuable and easy to follow to get started quickly._

## How it works

Many readers may wonder how does block-based-programming work and how to use blockly. Here I shall provide a simple example with the input layer block, one of the simplest blocks in the app.

Blockly allows you to define a block very easily by specifying a few attributes in a JSON/XML file. This will use the default UI for each block.

```json
{
    "type": "input_layer",
    "message0": "Input layer with shape of dataset",
    "colour": 120,
    "tooltip": "Uses the shape specified in input block",
    "nextStatement": null,
    "previousStatement": null
}
```

Each block has an associated block-code generator that defines what code it generates:

```javascript
// blockGenerator.js

import { pythonGenerator } from "blockly/python";
import * as Blockly from "blockly/core";

pythonGenerator.forBlock["input_layer"] = function (block) {
  return `keras.Input(shape=data.shape[1:]),\n`;
};
```

Lastly, you need to inject the blockly workspace to specify the location in the DOM and configurations:

```javascript
// main.js

Blockly.inject("blocklyDiv", {
    toolbox: toolboxJson,
    scrollbars: false,
    verticalLayout: true,
    toolboxPosition: "left",
});
```

You can learn more about our project by visiting our GitHub repository and trying out the app yourself!

{{< button url="https://github.com/supreme-gg-gg/block-ml" >}}BlockML GitHub!{{< /button >}}
