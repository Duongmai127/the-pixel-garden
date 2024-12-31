---
type: main-note
created:
  "{ date }": 
tags:
  - concept
  - HSU
  - paper-review
cssclasses:
  - page-white
excalidraw-plugin: parsed
excalidraw-open-md:
---

# Graph construction and Laplacian Matrix

## Core Concept

From a hyperspectral image with N pixels, we construct a graph with N nodes, where each node in the graph uniquely represents a pixel in the image.

To complete the graph, we need to establish edges (or weights) between nodes. In [[chenGraphBasedActive2023]], instead of connecting each node to every other N - 1 pixels, an edge is formed between a node and only its K-nearest neighbors (where K < N).

The nearest neighbors are identified based on the angular distance using an approximate nearest neighbor search, but the weight between a node and each of its K-nearest neighbors is computed as a function of their angular distance rather than being directly proportional to it.

We can represent the graph as an N x N weight matrix W, which originates from an adjacency matrix but with scaled weights. Each row has K non-zero entries (representing the weights between the current node and each of its K nearest neighbors) and zero-valued remaining N - K entries.

From W, we derive an N x N diagonal matrix D where each diagonal entry is a sum of all the entries of the respective row.

Finally, the Laplacian matrix D is computed as the difference between degree matrix D and weight matrix W, given by L = D - W

Later, we can modify the L matrix and represent it in terms of blocks as in [[Graph Learning Unmixing]]

## Source
- [[{{source}}]]

## Connections
- Project: [[Nearly Blind Hyperspectral]]
- Related Notes: 

## Questions & Ideas
- 

## Tags
#concept #hyperspectral