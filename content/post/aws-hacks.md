---
title: MapMatch
subtitle: Finding roommates with NLP powered by AWS
date: 2024-12-31
tags: ["python", "machine-learning", "aws", "hackathon"]
---

Cosine similarity is a simple way to measure how similar two vectors are, yet it inspired us to solve a complex roomate matching problem at AWS Hackathon hosted by IEEE UofT. Starting from semantic similarity, Pual, Eric, Hayson, and I (EngSci 2T8) built a recommendation system inspired by retrieval augmented generation (RAG) and graph theory to match roomates based on their preferences and personalities that won the hackathon.

$$
\text{similarity} = \cos(\theta) = \frac{A \cdot B}{\|A\| \|B\|}
$$

## The Problem

1. Existing roomate matching relies on limited criteria and lacks personalisation

2. Filling in forms is tedious and time-consuming

3. Presenting candidates in a list is not visually appealing nor informative

4. International students might find it difficult to describe themselves in English

## The Solution

{{< columns >}}
{{< figure link="/img/mapmatch/aws.png" caption="AWS Technolgoy we used" >}}
{{< column >}}
{{< figure link="/img/mapmatch/gallery.jpg" caption="Primitive frontend" >}}
{{< endcolumns >}}

After the user enters a text description of themselves, we compute high dimensional embeddings for extracted key phrases and store them in a vectorDB for efficiency. Then we use algorithms such as cosine similarity and L2 norm to find the k most similar profiles. These are graphed to show the connections between users.

In the next phase, users can also build a path on the graph to find a group of most compatible roomates based on mutual preferences and personalities. This enables roomate search for groups, in addition to pairs, of people who want to live together.

{{< button url="https://devpost.com/software/roomiematch-xoe75b" >}}View us on Devpost!{{< /button >}}
