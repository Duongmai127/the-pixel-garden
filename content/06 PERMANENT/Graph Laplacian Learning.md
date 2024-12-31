---
type: main-note
created: 2024-12-30T10:05
tags:
  - concept
  - HSU
  - paper-review
cssclasses:
  - page-white
excalidraw-plugin:
---

# Graph Laplacian Learning

## Core Concept

We use Graph Laplacian Learning to infer either the probability mass function (pmf) of **unlabeled** pixels given a minimal subset of labeled pixels with known ground truth values (i.e., one-hot (pseudo) vector). The way to infer the a function that is predictive of the world is via minimizing an objective function in [[Train a node function to predict class probabilities]] wherein the Laplacian matrix, and pixels come from the graph constructed using angular distance and KNN in [[Laplacian Matrix]]


We would train an optimal node function u that can output a vector of class probabilities for each and every pixel such that the class probability (i.e., a vector whose entries are nonnegative and sum up to 1) are as close to the ground truth.

In Graph Laplacian Learning, choosing a high-quality (over quantity) subset of labeled pixels to initialize the learning process (because the objective function depends on the value of the initial labeled pixels to train the node function) is crucial. In practice, we often start with a random subset. However, in [[chenGraphBasedActive2023]], they propose a novel initialization method with active learning to choose high quality labeled pixels. In fact, they achieved 50% improvement over state-of-the-art unsupervised hyperspectral unmixing methods by only using about 0.4% of training pixels.
## Source
- [[{{source}}]]

## Connections
- Project: [[Nearly Blind Hyperspectral]]
- Related Notes: 

## Questions & Ideas
- 

## Tags
#concept #hyperspectral