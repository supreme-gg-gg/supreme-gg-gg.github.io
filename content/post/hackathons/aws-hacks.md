---
title: MapMatch
subtitle: Finding roommates with NLP powered by AWS
date: 2024-12-31
tags: ["machine-learning", "hackathon", "nlp"]
skills: ["AWS", "postgresql", "TypeScript", "Supabase", "Express"]
---

What if looking for a roommate was as easy as a google search -- only but more accurate? Our answer is MapMatch. Inspired by retrieval augmented generation (RAG), we integrated semantic search, mind-map navigation, with AWS cloud technologies to match roommates based on their preferences and personalities.

{{< columns >}}
{{< figure link="/img/mapmatch/aws.png" caption="AWS Technolgoy we used" >}}
{{< column >}}
{{< figure link="/img/mapmatch/gallery.jpg" caption="Primitive frontend" >}}
{{< endcolumns >}}

<!--more-->

## The Problem

1. Existing roomate matching relies on limited criteria and lacks personalisation

2. Filling in forms is tedious and time-consuming

3. Presenting candidates in a list is not visually appealing nor informative

4. International students might find it difficult to describe themselves in English

## The Solution

Cosine similarity is a simple way to measure how similar two vectors are, yet it inspired my team to come up with an unique solution to the complex roomate matching problem. We built a recommendation system inspired by retrieval augmented generation (RAG) and graph theory to match roomates based on their preferences and personalities.

$$
\cos(\mathbf{x}_q, \mathbf{x}_i) = \frac{\mathbf{x}_q \cdot \mathbf{x}_i}{\|\mathbf{x}_q\| \|\mathbf{x}_i\|}
$$

After the user enters a text description of themselves, we compute high dimensional embeddings for extracted key phrases and store them in a vectorDB for efficiency. Then we use algorithms such as cosine similarity and L2 norm to find the k most similar profiles. These are graphed to show the connections between users.

In the next phase, users can also build a path on the graph to find a group of most compatible roomates based on mutual preferences and personalities. This enables roomate search for groups, in addition to pairs, of people who want to live together.

{{< button url="https://devpost.com/software/roomiematch-xoe75b" >}}View us on Devpost!{{< /button >}}
