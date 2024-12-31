---
type: main-note
created:
  2024-12-30T04:17
tags:
  - concept
  - HSU
  - paper-review
cssclasses:
  - page-white
excalidraw-plugin:
---

# Train a node function to predict class probabilities

## Core Concept
We need to pick a set of nodes in the graph for which we will acquire a set of corresponding labels (i.e. in our case, it could be an abundance vector or one-hot pseudo-label that denotes the most significant end-member of each pixel). Remember that each node in our graph represents a pixel in hyperspectral imaging.

Our goal is to train a node function that can predict the abundance map of all the remaining unlabeled (or/and labeled) nodes (pixels) from the nodes (pixels) that already have ground truth abundance map or pseudo-label. 

Usually, in a standard DNN problem, you would optimize the objective function w.r.t. the model's weights, i.e. tweaking the model weights so that our objective is optimized. In the [[chenGraphBasedActive2023]], instead of the weight matrix, we would tweak the node function to output the pmf for each node as close as possible to our ground truth + another objective. The first term ensures the smoothness of our node function; it encourages that the the class probabilities for every 2 nodes are as similar as possible if the weight connection is huge. The second term effectively mitigates the difference between the ground truth and predictions of the chosen pixels.

![[Pasted image 20241230044837.png]]
The objective can be rewritten with a slight modification to the first time -
![[Pasted image 20241230045143.png]]
As seen clearly, we can now utilize the Laplacian matrix and U matrix with ease which further facilitates the future process of minimizing it.
## Source
- [[{{source}}]]

## Connections
- Project: [[Nearly Blind Hyperspectral]]
- Related Notes: 

## Questions & Ideas
- 

## Tags
#concept #hyperspectral