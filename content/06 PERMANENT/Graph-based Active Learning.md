---
type: main-note
created:
  2024-12-30T10:38
tags:
  - concept
  - HSU
  - paper-review
cssclasses:
  - page-white
excalidraw-plugin:
---

# Graph-based Active Learning

## Core Concept
Graph-based Active Learning comes in picking the high-quality training pixels to train a [[Graph Learning Unmixing (GLU)]]. Interestingly, it incorporates [[Graph Laplacian Learning]] to produce the subset of high-quality pixels.

Step 1: Initialize a set of training pixels by picking a random subset of current pixels and acquiring their one-hot pseudo-labels via expert visual inspection (i.e., experts identify the most significant end-member out of all the known end-members and that translates into a one-hot vector).

Step 2: Apply [[Graph Laplacian Learning]] to infer the labels of all pixels outside of the training set, also known as unlabeled pixels

Step 3: Compute Acquisition values for each unlabeled pixel

Step 4: Based on the acquisition values, we take a subset of unlabeled pixels (the number of pixels depends on our strategy (sequential active learning or LocalMax)) and add it to the current training pixel set

Step 5: Repeat step 2-4 until our desired number of training pixels is reached

## Source
- [[{{source}}]]

## Connections
- Project: [[Nearly Blind Hyperspectral]]
- Related Notes: 

## Questions & Ideas
- 

## Tags
#concept #hyperspectral