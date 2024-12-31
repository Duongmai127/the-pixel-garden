---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - concept
  - HSU
  - paper-review
type: main-note
created: 2024-12-30T10:56
cssclasses:
  - page-white
---



## Graph Learning Unmixing
## Core Concept

Step 1: Use [[Graph-based Active Learning]] to identify M training pixels

Step 2:
2.1. Data preparation:
Concatenate M training pixels with entire N pixels (M + N) to form a data matrix of dimension $R^{(M+N)*(M+N)}$ 

2.2. Graph construction:
Construct a graph using [[Laplacian Matrix|KNN]] and compute the [[Laplacian Matrix]]. Break the Laplacian matrix into blocks form where:
* Diagonal blocks (unlabeled and labeled relationships)
* Off-diagonal blocks (relationship between labeled and unlabeled)
* 
2.3. Compute the abundance map: (This is another area where [[Graph Laplacian Learning]] comes in - this optimization problem can be solved via a closed-form solution rather than iterative procedures)

Compute the abundance map (columns are class probabilities vectors for all pixels) via a closed-form solution (using Laplacian blocks) and project it onto the spectral space to compute the final abundance map.

Unlike how [[Graph Laplacian Learning]] in [[Graph-based Active Learning]], it only stops at inferring the abundance map without doing the next step of inferring the class labels for all pixels.

2.4. Compute the end-member matrix:
Infer the end-member matrix from the abundance map via another closed-form solution.

GLU achieves efficiency through closed-form solutions, avoiding iterative computations.

We do need a drawing to illustrate the concepts
Drawbacks: we may need additional equations and prospective [[notations]] to make our notes self-contained 

## Source
- [[{{source}}]]

## Connections
- Project: [[Nearly Blind Hyperspectral]]
- Related Notes: 

## Questions & Ideas
- 

## Tags
#concept #hyperspectral

==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'


# Excalidraw Data

## Text Elements
Graph Laplacian Learning to infer 
class labels for unlabeled pixels ^wZYhf5hR

Given q end-members, acquire a 
one-hot pseudo-label vector q*
to identify the most significant 
end member of this node (pixel) ^deT23aRz

q* ^MiV6w5fr

q* ^wFFo0YPH

q* ^9MhNyvsZ

q* ^aygbncS5

q* ^6Mb5UAPh

q* ^3Ab7hFhM

q_k ^ZilBUolr

r ^chpBW1KM

q_k ^x5w4yQIH

r ^HlFxm2fV

q_k ^46MEYj75

r ^TtdrY5RF

q_k ^FsFBgK6h

r ^oiDQGsok

q_k ^bd1VPJfv

r
- ^2gxo2ML3

q_k ^JH4Y8vYx

r ^hAkrLov7

q_k ^ersMWGDF

where q_k could be {q_1, q_2, ..., q_k} 
amd k is the number of classes (end-members) ^6hx1kl3m

r ^vN3o3YbL

Acquisition function to all unlabeled pixels
to compute their respective values ^zhHfdbTt

where r is any arbitrary real-valued number ^98KPE6pk

Sequential Active Learning or LocalMax: ^ZylxnzgR

Add a query set of unlabeled pixels
to the current training pixel set
based on the acquisition values ^UOOxzty5

q* ^TpXEWWt5

q* ^lvG6x43Y

Repeat until the desired number of 
training pixels is reached ^0KN6axrt

The current set of
training pixels
(labeled pixel) ^7OcDiOhV

q* =  ^J77kkGYV

q* =  ^JJVw7IYd

q* =  ^5q0uBhjH

q* =  ^9lJEr5X6

One-hot pseudo-labeling vector (i.e., ground truth) for training pixels ^0xMiObAk

an example output vector for each node after Graph Laplacian Learning ^tfqswOUx

Terminate the loop until a number of 
M desired training pixels is reached
(Assume that M = 3 in our example) ^iDYRtLWN

q* ^5ktosQBE

q ^drcvBfPL

q ^AmHi7vAv

q ^drfiu944

q ^Cne5XkI2

q ^aIwamUtP

q ^fUOb4P51

q ^PpL7FJyZ

where q is a vector whose entries are probabilities over all given classes. 
Each entry is nonnegative and all entries sum up to 1 ^Ck3xCGah

For each output vector, infer the index of the entry with the highest probability value.
The index corresponds to a specific label (or class)  ^h6bdMYLx

all entries are non-negative and 
sum up to 1 ^Rq1bis6K

the K-th entry is the highest value,
so the K-end member is the class for this vector, 
and the one-hot pseudo-labeling is q ^49tadH25

Graph-based Active Learning to Pick Training Pixels ^cdDBf1MM

duplicate nodes ^a5vnBhpj

q* ^lR94zyFo

Construct another graph and compute the new Laplacian matrix ^RUXBzKWW

Suppose that originally we have a data matrix A of dimension q x N,
and a training data matrix q x M A^, we concatenate them and have
a new data matrix (M + N) x (M + N) A*
 ^yLCs6rYd

Break the Laplacian matrix into block form ^hQwOWGAQ

A_GLU is an abundance map where each column is the abundance vector of each pixel in the hyperspectral imaging ^CwKtrwaV

solved via a closed-form solution ^wx24keUZ

= max(0, S^0_GLU) ^QOqJB7Cp

Replace any negative entries with 0 effectively ^EEDxSV4U

%%
## Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.7.2",
	"elements": [
		{
			"id": "oKiBFM3fz3oegk-gz0mZD",
			"type": "arrow",
			"x": -2502.1601966395747,
			"y": -1239.7726078204505,
			"width": 335.15785618832234,
			"height": 0.8421245374177602,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a0",
			"roundness": {
				"type": 2
			},
			"seed": 783931135,
			"version": 136,
			"versionNonce": 811644241,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					335.15785618832234,
					0.8421245374177602
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "wZYhf5hR",
			"type": "text",
			"x": -2503.8444457144105,
			"y": -1309.6673382378026,
			"width": 328.53973388671875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a1",
			"roundness": null,
			"seed": 2089066271,
			"version": 175,
			"versionNonce": 505406257,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"text": "Graph Laplacian Learning to infer \nclass labels for unlabeled pixels",
			"rawText": "Graph Laplacian Learning to infer \nclass labels for unlabeled pixels",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph Laplacian Learning to infer \nclass labels for unlabeled pixels",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "DTaFSJqhzENeXJrf2fdxY",
			"type": "arrow",
			"x": -2643.7969539380947,
			"y": -1018.9028753150537,
			"width": 116.800048828125,
			"height": 105.5999755859375,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a2",
			"roundness": {
				"type": 2
			},
			"seed": 838951743,
			"version": 91,
			"versionNonce": 1929433727,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508927,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-116.800048828125,
					-105.5999755859375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "KRdXiCWtTDh4zLLZ_Bhg-",
				"focus": 0.3013954142251528,
				"gap": 13.640211707047477,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "CHSONzHtRNhIiQBpuPk-Z",
			"type": "rectangle",
			"x": -2650.196978352157,
			"y": -1014.1029485572412,
			"width": 361.60009765625,
			"height": 145.60009765625003,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"vIu0E_OdeubHpRycvMe5d",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a3",
			"roundness": {
				"type": 3
			},
			"seed": 2140185439,
			"version": 301,
			"versionNonce": 200510193,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "deT23aRz",
			"type": "text",
			"x": -2630.9969051099697,
			"y": -993.3028997291162,
			"width": 328.526611328125,
			"height": 103.20019531249991,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"vIu0E_OdeubHpRycvMe5d",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a4",
			"roundness": null,
			"seed": 897769343,
			"version": 360,
			"versionNonce": 1476854993,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"text": "Given q end-members, acquire a \none-hot pseudo-label vector q*\nto identify the most significant \nend member of this node (pixel)",
			"rawText": "Given q end-members, acquire a \none-hot pseudo-label vector q*\nto identify the most significant \nend member of this node (pixel)",
			"fontSize": 20.640039062499984,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given q end-members, acquire a \none-hot pseudo-label vector q*\nto identify the most significant \nend member of this node (pixel)",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "ARY0mohjbXI61xcGwOYCs",
			"type": "arrow",
			"x": -2896.5970027662197,
			"y": -1015.7028631080225,
			"width": 94.4000244140625,
			"height": 105.60000610351562,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a5",
			"roundness": {
				"type": 2
			},
			"seed": 1176016799,
			"version": 144,
			"versionNonce": 627059359,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508928,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					94.4000244140625,
					-105.60000610351562
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "KRdXiCWtTDh4zLLZ_Bhg-",
				"focus": -0.31953456792643536,
				"gap": 14.940222281625587,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "njCcbZVMsOZAyD9yDoyap",
			"type": "ellipse",
			"x": -2589.847063801376,
			"y": -1238.6653493751123,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a6",
			"roundness": {
				"type": 2
			},
			"seed": 125979583,
			"version": 142,
			"versionNonce": 578208913,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "KRdXiCWtTDh4zLLZ_Bhg-",
			"type": "ellipse",
			"x": -2809.5286176922064,
			"y": -1177.4568697447926,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a7",
			"roundness": {
				"type": 2
			},
			"seed": 903904223,
			"version": 127,
			"versionNonce": 1496451697,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "DTaFSJqhzENeXJrf2fdxY",
					"type": "arrow"
				},
				{
					"id": "ARY0mohjbXI61xcGwOYCs",
					"type": "arrow"
				}
			],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "8Js8X2EYyw6SmZaBMCaPC",
			"type": "ellipse",
			"x": -2818.6470210767666,
			"y": -1328.6653341163233,
			"width": 38.4000244140625,
			"height": 40.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a8",
			"roundness": {
				"type": 2
			},
			"seed": 893626367,
			"version": 223,
			"versionNonce": 939226129,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "_OmF6YOroqr4KEH_QP86M",
			"type": "ellipse",
			"x": -2734.6470515943447,
			"y": -1377.0653432715967,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "a9",
			"roundness": {
				"type": 2
			},
			"seed": 330059807,
			"version": 144,
			"versionNonce": 1232390641,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "VjV9_CqmVyFs7arhzPSJ0",
			"type": "ellipse",
			"x": -2849.047045490829,
			"y": -1240.265355478628,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aA",
			"roundness": {
				"type": 2
			},
			"seed": 1259009087,
			"version": 144,
			"versionNonce": 1896375249,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "RxsvGtYoxysM3TvOTl_9B",
			"type": "ellipse",
			"x": -2721.047076008407,
			"y": -1204.265355478628,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aB",
			"roundness": {
				"type": 2
			},
			"seed": 1128272991,
			"version": 144,
			"versionNonce": 2060304817,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "rVirp1hSSvZi6JjU4jIea",
			"type": "ellipse",
			"x": -2636.247027180282,
			"y": -1349.0653432715967,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aC",
			"roundness": {
				"type": 2
			},
			"seed": 337391743,
			"version": 144,
			"versionNonce": 1139565457,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "uwZKWQ33EM2k14nAvj3pY",
			"type": "line",
			"x": -2788.247027180282,
			"y": -1327.8653463233545,
			"width": 55.20001220703125,
			"height": 20.800018310546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aD",
			"roundness": {
				"type": 2
			},
			"seed": 123717791,
			"version": 56,
			"versionNonce": 412862833,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.20001220703125,
					-20.800018310546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "a2uqPMGm8GbSSvnTznTeD",
			"type": "line",
			"x": -2812.2470576978603,
			"y": -1291.8653463233545,
			"width": 21.5999755859375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aE",
			"roundness": {
				"type": 2
			},
			"seed": 1522228415,
			"version": 83,
			"versionNonce": 1378054993,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.5999755859375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "o4WdUBAomh0h1dM7yKN-V",
			"type": "line",
			"x": -2794.6470515943447,
			"y": -1169.4653524268701,
			"width": 31.199981689453125,
			"height": 36,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aF",
			"roundness": {
				"type": 2
			},
			"seed": 1104112863,
			"version": 63,
			"versionNonce": 886759729,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-31.199981689453125,
					-36
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "wD3uqRcJ54ze95-TuzksK",
			"type": "line",
			"x": -2781.047014973251,
			"y": -1174.265370737417,
			"width": 97.5999755859375,
			"height": 84.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aG",
			"roundness": {
				"type": 2
			},
			"seed": 674003199,
			"version": 105,
			"versionNonce": 237605649,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					-84.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "_PdO8UFfoqMi88ZbNbkeF",
			"type": "line",
			"x": -2627.4470393873135,
			"y": -1319.0653585303858,
			"width": 81.5999755859375,
			"height": 29.600006103515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aH",
			"roundness": {
				"type": 2
			},
			"seed": 861077791,
			"version": 87,
			"versionNonce": 310839537,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-81.5999755859375,
					-29.600006103515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "22viNLa2qVA2bA29WMwso",
			"type": "line",
			"x": -2606.6470515943447,
			"y": -1315.0653585303858,
			"width": 28.79998779296875,
			"height": 78.39999389648438,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aI",
			"roundness": {
				"type": 2
			},
			"seed": 78873919,
			"version": 83,
			"versionNonce": 2071642833,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.79998779296875,
					78.39999389648438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "yByOVQVV6F6Q6B6kd4Pc7",
			"type": "line",
			"x": -2685.047014973251,
			"y": -1259.0653585303858,
			"width": 5.60003662109375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aJ",
			"roundness": {
				"type": 2
			},
			"seed": 1001293151,
			"version": 77,
			"versionNonce": 1704738993,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.60003662109375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "GlyQL0M_xiqIwsf4yBX4b",
			"type": "line",
			"x": -2684.247027180282,
			"y": -1259.8653463233545,
			"width": 97.5999755859375,
			"height": 30.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aK",
			"roundness": {
				"type": 2
			},
			"seed": 932479359,
			"version": 99,
			"versionNonce": 1855128209,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					30.399993896484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "uLtUxYALO7r5pniHXJr7y",
			"type": "ellipse",
			"x": -2714.791775586943,
			"y": -1303.7726592184767,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aL",
			"roundness": {
				"type": 2
			},
			"seed": 430307743,
			"version": 374,
			"versionNonce": 320243825,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "MiV6w5fr",
			"type": "text",
			"x": -2795.7969539380947,
			"y": -1169.3028997291162,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"pVLDG-5rRQ5w6tBYhhLe3",
				"xcc61ziLAMb4_gMfsNoHO",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aM",
			"roundness": null,
			"seed": 118713791,
			"version": 119,
			"versionNonce": 1290687057,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "AynFqrpE2ltu3chTtxIek",
			"type": "ellipse",
			"x": -2316.0568959639695,
			"y": -1636.7682401441307,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aN",
			"roundness": {
				"type": 2
			},
			"seed": 721247711,
			"version": 271,
			"versionNonce": 1894899761,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "DTaFSJqhzENeXJrf2fdxY",
					"type": "arrow"
				},
				{
					"id": "ARY0mohjbXI61xcGwOYCs",
					"type": "arrow"
				}
			],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "g6GvCzz9ZqmKmBULqphZR",
			"type": "ellipse",
			"x": -2355.5753237625922,
			"y": -1699.576725877966,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aO",
			"roundness": {
				"type": 2
			},
			"seed": 2020887039,
			"version": 288,
			"versionNonce": 1292415505,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "QfVL899P0UMRbFoh-39_E",
			"type": "ellipse",
			"x": -2096.375342073139,
			"y": -1697.9767197744504,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aP",
			"roundness": {
				"type": 2
			},
			"seed": 746107423,
			"version": 288,
			"versionNonce": 103434225,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "uPAF7Wt5HKFZ_lVPZ3l0e",
			"type": "ellipse",
			"x": -2325.1752993485297,
			"y": -1787.9767045156614,
			"width": 38.4000244140625,
			"height": 40.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aQ",
			"roundness": {
				"type": 2
			},
			"seed": 268113471,
			"version": 371,
			"versionNonce": 912138705,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "2gR4Jq11rXZo7JEAsaXv4",
			"type": "ellipse",
			"x": -2241.175329866108,
			"y": -1836.3767136709348,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aR",
			"roundness": {
				"type": 2
			},
			"seed": 2044458591,
			"version": 291,
			"versionNonce": 1253818289,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "IiWiQTj_G0i5fzOx3Zb-H",
			"type": "ellipse",
			"x": -2227.5753542801704,
			"y": -1663.576725877966,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aS",
			"roundness": {
				"type": 2
			},
			"seed": 283890303,
			"version": 291,
			"versionNonce": 560636305,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "SXfQrCL1KHxLSBEIzl7Ht",
			"type": "ellipse",
			"x": -2142.7753054520454,
			"y": -1808.3767136709348,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aT",
			"roundness": {
				"type": 2
			},
			"seed": 1307257503,
			"version": 292,
			"versionNonce": 1738688369,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false
		},
		{
			"id": "wOxGpUp8eevnUecJhW1bw",
			"type": "line",
			"x": -2294.7753054520454,
			"y": -1787.1767167226926,
			"width": 55.20001220703125,
			"height": 20.800018310546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aU",
			"roundness": {
				"type": 2
			},
			"seed": 1032486591,
			"version": 203,
			"versionNonce": 933900625,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.20001220703125,
					-20.800018310546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "RGZXm7SV31o26goTzNLye",
			"type": "line",
			"x": -2318.7753359696235,
			"y": -1751.1767167226926,
			"width": 21.5999755859375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aV",
			"roundness": {
				"type": 2
			},
			"seed": 40521439,
			"version": 230,
			"versionNonce": 1993989937,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.5999755859375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "cMwg3UW0yZYhiHS5DN1-L",
			"type": "line",
			"x": -2301.175329866108,
			"y": -1628.7767228262082,
			"width": 31.199981689453125,
			"height": 36,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aW",
			"roundness": {
				"type": 2
			},
			"seed": 387652351,
			"version": 210,
			"versionNonce": 1939394833,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508770,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-31.199981689453125,
					-36
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "SPoH_J871CpNE0HPgMAwK",
			"type": "line",
			"x": -2287.575293245014,
			"y": -1633.5767411367551,
			"width": 97.5999755859375,
			"height": 84.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aX",
			"roundness": {
				"type": 2
			},
			"seed": 1344103199,
			"version": 252,
			"versionNonce": 1130268401,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					-84.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "udmniHSkK8K6NA8VNFEwx",
			"type": "line",
			"x": -2133.9753176590766,
			"y": -1778.3767289297239,
			"width": 81.5999755859375,
			"height": 29.600006103515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aY",
			"roundness": {
				"type": 2
			},
			"seed": 501327679,
			"version": 234,
			"versionNonce": 1622311121,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-81.5999755859375,
					-29.600006103515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "tnzwLESmQ9BfqWod1QdH4",
			"type": "line",
			"x": -2113.175329866108,
			"y": -1774.3767289297239,
			"width": 28.79998779296875,
			"height": 78.39999389648438,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aZ",
			"roundness": {
				"type": 2
			},
			"seed": 248014687,
			"version": 230,
			"versionNonce": 153894577,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.79998779296875,
					78.39999389648438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "DPPfdQbZYvdnCVcC7fEVc",
			"type": "line",
			"x": -2191.575293245014,
			"y": -1718.3767289297239,
			"width": 5.60003662109375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aa",
			"roundness": {
				"type": 2
			},
			"seed": 287449983,
			"version": 224,
			"versionNonce": 1534279825,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.60003662109375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "cdPPWyTR0nu1Mw99HLb7I",
			"type": "line",
			"x": -2190.7753054520454,
			"y": -1719.1767167226926,
			"width": 97.5999755859375,
			"height": 30.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ab",
			"roundness": {
				"type": 2
			},
			"seed": 1966037919,
			"version": 246,
			"versionNonce": 893322865,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					30.399993896484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "zRUfeUeEUTQm9etX8s_Yx",
			"type": "ellipse",
			"x": -2219.2973449561705,
			"y": -1763.0840296178153,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ac",
			"roundness": {
				"type": 2
			},
			"seed": 790663103,
			"version": 522,
			"versionNonce": 1364660305,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "wFFo0YPH",
			"type": "text",
			"x": -2302.325232209858,
			"y": -1628.6142701284543,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"LZ5kCPVaifyAZgyBrdPMT",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ad",
			"roundness": null,
			"seed": 1494630367,
			"version": 266,
			"versionNonce": 630382129,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "herLRhIaS0L96mWNQufFD",
			"type": "ellipse",
			"x": 823.2157949252237,
			"y": -1931.4191747922368,
			"width": 139.14542157148824,
			"height": 119.26748013168817,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ae",
			"roundness": {
				"type": 2
			},
			"seed": 1965091839,
			"version": 595,
			"versionNonce": 14282769,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "DTaFSJqhzENeXJrf2fdxY",
					"type": "arrow"
				},
				{
					"id": "ARY0mohjbXI61xcGwOYCs",
					"type": "arrow"
				}
			],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "MBsrn_uN1TOJOU3yZsxn6",
			"type": "ellipse",
			"x": 2126.9300457622767,
			"y": -1996.8477287821925,
			"width": 139.14542157148824,
			"height": 119.26748013168817,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "af",
			"roundness": {
				"type": 2
			},
			"seed": 1866535967,
			"version": 789,
			"versionNonce": 1763952113,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "DTaFSJqhzENeXJrf2fdxY",
					"type": "arrow"
				},
				{
					"id": "ARY0mohjbXI61xcGwOYCs",
					"type": "arrow"
				}
			],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "NdRgog8HDPwH7aEnUWBAJ",
			"type": "ellipse",
			"x": 719.567672889194,
			"y": -2096.151983177538,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ag",
			"roundness": {
				"type": 2
			},
			"seed": 1600600127,
			"version": 611,
			"versionNonce": 964157393,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "xdBq2k0Si22yYK1MbOb2w",
			"type": "ellipse",
			"x": 1399.3920695171828,
			"y": -2091.9555199801493,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ah",
			"roundness": {
				"type": 2
			},
			"seed": 192141407,
			"version": 611,
			"versionNonce": 2146287025,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "NqR8qTMNVN928edtIRGqU",
			"type": "ellipse",
			"x": 799.3002335169444,
			"y": -2328.005634352945,
			"width": 100.7147965738159,
			"height": 107.00937130858179,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ai",
			"roundness": {
				"type": 2
			},
			"seed": 691500159,
			"version": 694,
			"versionNonce": 464314257,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "kYsaIQVENhIVIzDVELHMi",
			"type": "ellipse",
			"x": 2103.0144843539974,
			"y": -2393.4341883429,
			"width": 100.7147965738159,
			"height": 107.00937130858179,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aj",
			"roundness": {
				"type": 2
			},
			"seed": 1618119839,
			"version": 885,
			"versionNonce": 451724657,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "AMuvOoavpaTvgqXYqxgVL",
			"type": "ellipse",
			"x": 1019.6136309097524,
			"y": -2454.9481858389036,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ak",
			"roundness": {
				"type": 2
			},
			"seed": 215326911,
			"version": 614,
			"versionNonce": 1492447057,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "HIFLdHMfeuL29bXJ-ndcj",
			"type": "ellipse",
			"x": 1055.2833679853607,
			"y": -2001.7319214202444,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "al",
			"roundness": {
				"type": 2
			},
			"seed": 1073819871,
			"version": 614,
			"versionNonce": 1545395505,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "6iIWq1NyrJoFx5iyRaX9B",
			"type": "ellipse",
			"x": 1277.6951970790578,
			"y": -2381.510360027675,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "am",
			"roundness": {
				"type": 2
			},
			"seed": 59096319,
			"version": 615,
			"versionNonce": 1942753041,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "ZESC7nHmrwC_WGZT2SLtV",
			"type": "ellipse",
			"x": 2581.4094479161113,
			"y": -2446.9389140176304,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "an",
			"roundness": {
				"type": 2
			},
			"seed": 1524876575,
			"version": 806,
			"versionNonce": 377095409,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "eLs12eA8iP1HQaoAx1KH8",
			"type": "ellipse",
			"x": 1076.9947610853465,
			"y": -2262.717637098531,
			"width": 139.14542157148824,
			"height": 119.26748013168817,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ao",
			"roundness": {
				"type": 2
			},
			"seed": 93047103,
			"version": 845,
			"versionNonce": 2142125777,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "9MhNyvsZ",
			"type": "text",
			"x": 859.2309210278254,
			"y": -1910.033109446479,
			"width": 55.80677795410156,
			"height": 65.56948733145406,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ap",
			"roundness": null,
			"seed": 14567775,
			"version": 589,
			"versionNonce": 234896561,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 52.45558986516325,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "aygbncS5",
			"type": "text",
			"x": 2162.945171864879,
			"y": -1975.4616634364343,
			"width": 55.80677795410156,
			"height": 65.56948733145406,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aq",
			"roundness": null,
			"seed": 1244382591,
			"version": 782,
			"versionNonce": 1628929681,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 52.45558986516325,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "KySlqjJCCWhIzdtmafSW8",
			"type": "ellipse",
			"x": -1022.9748540161054,
			"y": -932.8764421494529,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ar",
			"roundness": {
				"type": 2
			},
			"seed": 1622457759,
			"version": 526,
			"versionNonce": 933987441,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "ApwEKzprc6Fu3lKLnYOVO",
			"type": "ellipse",
			"x": -1242.6564079069367,
			"y": -871.6679625191332,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "as",
			"roundness": {
				"type": 2
			},
			"seed": 128561599,
			"version": 511,
			"versionNonce": 226741841,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "DTaFSJqhzENeXJrf2fdxY",
					"type": "arrow"
				},
				{
					"id": "ARY0mohjbXI61xcGwOYCs",
					"type": "arrow"
				}
			],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "NLW--9zeuXbhdjTlGuWYH",
			"type": "ellipse",
			"x": -1251.774811291496,
			"y": -1022.8764268906639,
			"width": 38.4000244140625,
			"height": 40.79998779296875,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "at",
			"roundness": {
				"type": 2
			},
			"seed": 1210786271,
			"version": 609,
			"versionNonce": 2037898289,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "Ho1gBzfl29treC0tIse8K",
			"type": "ellipse",
			"x": -1167.7748418090741,
			"y": -1071.2764360459373,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "au",
			"roundness": {
				"type": 2
			},
			"seed": 860458495,
			"version": 530,
			"versionNonce": 1265577489,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "DJbqGdqJLIk7VnqABsTIu",
			"type": "ellipse",
			"x": -1282.1748357055585,
			"y": -934.4764482529686,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "av",
			"roundness": {
				"type": 2
			},
			"seed": 1678079519,
			"version": 530,
			"versionNonce": 1784759281,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "MkYCjEIlOXZt3bn_Vw7nw",
			"type": "ellipse",
			"x": -1154.1748662231366,
			"y": -898.4764482529686,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "aw",
			"roundness": {
				"type": 2
			},
			"seed": 1095719487,
			"version": 566,
			"versionNonce": 1918213585,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "FwaxqvLhWbL1S7xR-NYJD",
			"type": "ellipse",
			"x": -1069.3748173950116,
			"y": -1043.2764360459373,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ax",
			"roundness": {
				"type": 2
			},
			"seed": 506463,
			"version": 531,
			"versionNonce": 308526001,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "7FZAnN1J7eeXXgCmwDWwz",
			"type": "line",
			"x": -1221.3748173950116,
			"y": -1022.0764390976951,
			"width": 55.20001220703125,
			"height": 20.800018310546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "ay",
			"roundness": {
				"type": 2
			},
			"seed": 1694439039,
			"version": 441,
			"versionNonce": 716381585,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.20001220703125,
					-20.800018310546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "2QWZ4565RWWC_MCG2NzcI",
			"type": "line",
			"x": -1245.3748479125898,
			"y": -986.0764390976951,
			"width": 21.5999755859375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "az",
			"roundness": {
				"type": 2
			},
			"seed": 1190522527,
			"version": 468,
			"versionNonce": 712721265,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.5999755859375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Nt83rLbEjDxtyPY6DZfRV",
			"type": "line",
			"x": -1227.7748418090741,
			"y": -863.6764452012108,
			"width": 31.199981689453125,
			"height": 36,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b00",
			"roundness": {
				"type": 2
			},
			"seed": 1352450751,
			"version": 448,
			"versionNonce": 771992913,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-31.199981689453125,
					-36
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ZfK6Mio6jxBiOdI8CHiK5",
			"type": "line",
			"x": -1214.1748051879804,
			"y": -868.4764635117576,
			"width": 97.5999755859375,
			"height": 84.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b01",
			"roundness": {
				"type": 2
			},
			"seed": 43258591,
			"version": 490,
			"versionNonce": 1554242353,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					-84.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "VdihnfwIqtpJMVIyHJJ8B",
			"type": "line",
			"x": -1060.5748296020429,
			"y": -1013.2764513047264,
			"width": 81.5999755859375,
			"height": 29.600006103515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b02",
			"roundness": {
				"type": 2
			},
			"seed": 1970036479,
			"version": 472,
			"versionNonce": 113462545,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-81.5999755859375,
					-29.600006103515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "uc6yVCLi_V1_4huZZ0gAI",
			"type": "line",
			"x": -1039.7748418090741,
			"y": -1009.2764513047264,
			"width": 28.79998779296875,
			"height": 78.39999389648438,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b03",
			"roundness": {
				"type": 2
			},
			"seed": 1537615647,
			"version": 468,
			"versionNonce": 64586481,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.79998779296875,
					78.39999389648438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "oZvnfenTSPbq4PPORJCcy",
			"type": "line",
			"x": -1118.1748051879804,
			"y": -953.2764513047264,
			"width": 5.60003662109375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b04",
			"roundness": {
				"type": 2
			},
			"seed": 1135733567,
			"version": 462,
			"versionNonce": 1349385425,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.60003662109375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "O6U9u22_UADo6I6TWDo6p",
			"type": "line",
			"x": -1117.3748173950116,
			"y": -954.0764390976951,
			"width": 97.5999755859375,
			"height": 30.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b05",
			"roundness": {
				"type": 2
			},
			"seed": 435170143,
			"version": 484,
			"versionNonce": 1813527217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					30.399993896484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "UbELze6X3BeG1FPUNxkfJ",
			"type": "ellipse",
			"x": -1147.9195658016733,
			"y": -997.9837519928174,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b06",
			"roundness": {
				"type": 2
			},
			"seed": 1790011263,
			"version": 760,
			"versionNonce": 2004860049,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "6Mb5UAPh",
			"type": "text",
			"x": -1228.9247441528241,
			"y": -863.5139925034568,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b07",
			"roundness": null,
			"seed": 1681268639,
			"version": 504,
			"versionNonce": 308019825,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "Sb5e_Q70xwGUoA6x2DtNf",
			"type": "ellipse",
			"x": -1832.8127250525595,
			"y": -590.414875890264,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b08",
			"roundness": {
				"type": 2
			},
			"seed": 414110655,
			"version": 703,
			"versionNonce": 2037681233,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "_q15RdDjGir51QqqUgCLm",
			"type": "ellipse",
			"x": -2052.49427894339,
			"y": -530.9841469109858,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b09",
			"roundness": {
				"type": 2
			},
			"seed": 3933151,
			"version": 687,
			"versionNonce": 1688263217,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "DTaFSJqhzENeXJrf2fdxY",
					"type": "arrow"
				},
				{
					"id": "ARY0mohjbXI61xcGwOYCs",
					"type": "arrow"
				}
			],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "bfclCPMIxoU93ThDeBK2R",
			"type": "ellipse",
			"x": -2061.61268232795,
			"y": -682.1926112825165,
			"width": 38.4000244140625,
			"height": 40.79998779296875,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0A",
			"roundness": {
				"type": 2
			},
			"seed": 988688383,
			"version": 784,
			"versionNonce": 617114641,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "cofc8P49o6CuhuBkz-DgN",
			"type": "ellipse",
			"x": -1977.6127128455282,
			"y": -730.59262043779,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0B",
			"roundness": {
				"type": 2
			},
			"seed": 314955807,
			"version": 705,
			"versionNonce": 31638001,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "-iZqulP16eakxDyTO7Jj9",
			"type": "ellipse",
			"x": -2092.0127067420126,
			"y": -593.7926326448212,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0C",
			"roundness": {
				"type": 2
			},
			"seed": 1035172927,
			"version": 705,
			"versionNonce": 1492605905,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "mAtnY1IS9pcavkMwidmxL",
			"type": "ellipse",
			"x": -1956.9014633880633,
			"y": -559.5704511127033,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0D",
			"roundness": {
				"type": 2
			},
			"seed": 1603771487,
			"version": 720,
			"versionNonce": 2048768433,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "yZRvuQs2IS5kUM6UFnv9Y",
					"type": "arrow"
				}
			],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "aDfSbUKDxTSk27e83U73Y",
			"type": "ellipse",
			"x": -1879.2126884314657,
			"y": -702.59262043779,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0E",
			"roundness": {
				"type": 2
			},
			"seed": 1279441023,
			"version": 705,
			"versionNonce": 239976817,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "NzDqXzOPJIxZb__abZq9m",
			"type": "line",
			"x": -2031.2126884314657,
			"y": -681.3926234895478,
			"width": 55.20001220703125,
			"height": 20.800018310546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0F",
			"roundness": {
				"type": 2
			},
			"seed": 158683295,
			"version": 616,
			"versionNonce": 785804113,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.20001220703125,
					-20.800018310546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "A_Tbpg3Y00XxrYg64ccHm",
			"type": "line",
			"x": -2055.212718949044,
			"y": -645.3926234895478,
			"width": 21.5999755859375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0G",
			"roundness": {
				"type": 2
			},
			"seed": 283108543,
			"version": 643,
			"versionNonce": 1886312753,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.5999755859375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "D-wW89cX9zMCoXpf-8lFf",
			"type": "line",
			"x": -2037.6127128455282,
			"y": -522.9926295930634,
			"width": 31.199981689453125,
			"height": 36,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0H",
			"roundness": {
				"type": 2
			},
			"seed": 1378022623,
			"version": 623,
			"versionNonce": 612272913,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-31.199981689453125,
					-36
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "aAp4DKJeAvbneo14EHqGp",
			"type": "line",
			"x": -2024.0126762244345,
			"y": -527.7926479036103,
			"width": 97.5999755859375,
			"height": 84.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0I",
			"roundness": {
				"type": 2
			},
			"seed": 1959723263,
			"version": 665,
			"versionNonce": 58523889,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					-84.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ZW_s2O-3n5gemwc72hY3d",
			"type": "line",
			"x": -1870.412700638497,
			"y": -672.592635696579,
			"width": 81.5999755859375,
			"height": 29.600006103515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0J",
			"roundness": {
				"type": 2
			},
			"seed": 1516538143,
			"version": 647,
			"versionNonce": 1257355985,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-81.5999755859375,
					-29.600006103515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "bJO6wGJ4ZS-WDqZERwn7d",
			"type": "line",
			"x": -1849.6127128455282,
			"y": -668.592635696579,
			"width": 28.79998779296875,
			"height": 78.39999389648438,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0K",
			"roundness": {
				"type": 2
			},
			"seed": 1616121151,
			"version": 643,
			"versionNonce": 460601521,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.79998779296875,
					78.39999389648438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "3sB6EPcQNvoABHbiJggE7",
			"type": "line",
			"x": -1928.0126762244345,
			"y": -612.592635696579,
			"width": 5.60003662109375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0L",
			"roundness": {
				"type": 2
			},
			"seed": 1644039519,
			"version": 637,
			"versionNonce": 380369553,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.60003662109375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "oCKTIB9B5ayAIs9Yc3lWx",
			"type": "line",
			"x": -1927.2126884314657,
			"y": -612.5037481640268,
			"width": 97.5999755859375,
			"height": 30.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0M",
			"roundness": {
				"type": 2
			},
			"seed": 2058553727,
			"version": 660,
			"versionNonce": 1028685937,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					30.399993896484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "_HRh-_eWaipflIaP5gBdk",
			"type": "ellipse",
			"x": -1955.9796861870855,
			"y": -657.2999363846702,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0N",
			"roundness": {
				"type": 2
			},
			"seed": 129204639,
			"version": 937,
			"versionNonce": 220809809,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false
		},
		{
			"id": "3Ab7hFhM",
			"type": "text",
			"x": -2038.7626151892782,
			"y": -522.8301768953095,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0O",
			"roundness": null,
			"seed": 1781527999,
			"version": 679,
			"versionNonce": 1594742833,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "ZilBUolr",
			"type": "text",
			"x": -1020.0976068126256,
			"y": -925.8827424109795,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0P",
			"roundness": null,
			"seed": 155772383,
			"version": 417,
			"versionNonce": 82160145,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "chpBW1KM",
			"type": "text",
			"x": -1816.2788986291462,
			"y": -585.1989268028321,
			"width": 8,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0Q",
			"roundness": null,
			"seed": 336515583,
			"version": 619,
			"versionNonce": 665337841,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "r",
			"rawText": "r",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "x5w4yQIH",
			"type": "text",
			"x": -1137.890173103462,
			"y": -984.2009741670163,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0R",
			"roundness": null,
			"seed": 58866207,
			"version": 471,
			"versionNonce": 1700600273,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "HlFxm2fV",
			"type": "text",
			"x": -1935.5259881799257,
			"y": -644.9716818188122,
			"width": 8,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0S",
			"roundness": null,
			"seed": 1553178175,
			"version": 682,
			"versionNonce": 790345649,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "r",
			"rawText": "r",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "46MEYj75",
			"type": "text",
			"x": -1063.708377116247,
			"y": -1032.2009630697153,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0T",
			"roundness": null,
			"seed": 841186911,
			"version": 493,
			"versionNonce": 1728813457,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508771,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "TtdrY5RF",
			"type": "text",
			"x": -1862.7987154526527,
			"y": -697.3352959878462,
			"width": 8,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0U",
			"roundness": null,
			"seed": 1728207487,
			"version": 700,
			"versionNonce": 1046757233,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "r",
			"rawText": "r",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "FsFBgK6h",
			"type": "text",
			"x": -1164.072146647496,
			"y": -1064.2009741670163,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0V",
			"roundness": null,
			"seed": 804303519,
			"version": 465,
			"versionNonce": 1399662929,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "oiDQGsok",
			"type": "text",
			"x": -1963.1625959569137,
			"y": -724.9716818188122,
			"width": 8,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0W",
			"roundness": null,
			"seed": 1436485311,
			"version": 673,
			"versionNonce": 259905329,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "r",
			"rawText": "r",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "bd1VPJfv",
			"type": "text",
			"x": -1242.617512414542,
			"y": -1013.2918277714198,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0X",
			"roundness": null,
			"seed": 917362399,
			"version": 495,
			"versionNonce": 1157482769,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "2gxo2ML3",
			"type": "text",
			"x": -2047.5261657367437,
			"y": -671.1533779303179,
			"width": 8,
			"height": 41.27274946732952,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0Y",
			"roundness": null,
			"seed": 162374399,
			"version": 695,
			"versionNonce": 224689905,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "r\n-",
			"rawText": "r\n-",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r\n-",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "JH4Y8vYx",
			"type": "text",
			"x": -1276.07199128528,
			"y": -931.837415484488,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0Z",
			"roundness": null,
			"seed": 1595861791,
			"version": 499,
			"versionNonce": 1731819729,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "hAkrLov7",
			"type": "text",
			"x": -2079.5260103745277,
			"y": -586.7899191234997,
			"width": 8,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0a",
			"roundness": null,
			"seed": 1668427583,
			"version": 709,
			"versionNonce": 336869041,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "r",
			"rawText": "r",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "ersMWGDF",
			"type": "text",
			"x": -1146.617534609144,
			"y": -892.5645661414483,
			"width": 28.948486328125,
			"height": 20.63637473366476,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0b",
			"roundness": null,
			"seed": 1627909983,
			"version": 496,
			"versionNonce": 916207761,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q_k",
			"rawText": "q_k",
			"fontSize": 16.509099786931806,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q_k",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "6hx1kl3m",
			"type": "text",
			"x": -1331.3704672529666,
			"y": -805.155480781008,
			"width": 445.23968505859375,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0c",
			"roundness": null,
			"seed": 36744063,
			"version": 528,
			"versionNonce": 814284401,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "where q_k could be {q_1, q_2, ..., q_k} \namd k is the number of classes (end-members)",
			"rawText": "where q_k could be {q_1, q_2, ..., q_k} \namd k is the number of classes (end-members)",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "where q_k could be {q_1, q_2, ..., q_k} \namd k is the number of classes (end-members)",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "yZRvuQs2IS5kUM6UFnv9Y",
			"type": "arrow",
			"x": -1944.0972801987482,
			"y": -537.0171641075196,
			"width": 7.353601937342205,
			"height": 7.030263573232332,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0d",
			"roundness": {
				"type": 2
			},
			"seed": 1395450783,
			"version": 253,
			"versionNonce": 1583316671,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "vN3o3YbL"
				}
			],
			"updated": 1735665508928,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					7.353601937342205,
					-7.030263573232332
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "mAtnY1IS9pcavkMwidmxL",
				"focus": -0.030264896662929454,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "mAtnY1IS9pcavkMwidmxL",
				"focus": 0.030264896662945927,
				"gap": 1,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "vN3o3YbL",
			"type": "text",
			"x": -1944.920479230077,
			"y": -553.0322958941358,
			"width": 9,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0e",
			"roundness": null,
			"seed": 70064063,
			"version": 56,
			"versionNonce": 1623119409,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "r",
			"rawText": "r",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "yZRvuQs2IS5kUM6UFnv9Y",
			"originalText": "r",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "bL7rugPUDs1rPuL4f_O2Y",
			"type": "arrow",
			"x": -1180.831990858278,
			"y": -725.5435630758141,
			"width": 506.8586985142041,
			"height": 152.01968935285487,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0f",
			"roundness": {
				"type": 2
			},
			"seed": 1800521695,
			"version": 498,
			"versionNonce": 1673979921,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-506.8586985142041,
					152.01968935285487
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "zhHfdbTt",
			"type": "text",
			"x": -1424.9611684480815,
			"y": -626.9757765697736,
			"width": 409.3197326660156,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0g",
			"roundness": null,
			"seed": 1185641471,
			"version": 455,
			"versionNonce": 1404157425,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "Acquisition function to all unlabeled pixels\nto compute their respective values",
			"rawText": "Acquisition function to all unlabeled pixels\nto compute their respective values",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Acquisition function to all unlabeled pixels\nto compute their respective values",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "98KPE6pk",
			"type": "text",
			"x": -2097.6232891019545,
			"y": -463.2219341282839,
			"width": 411.85968017578125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0h",
			"roundness": null,
			"seed": 1044028447,
			"version": 171,
			"versionNonce": 260495313,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "where r is any arbitrary real-valued number",
			"rawText": "where r is any arbitrary real-valued number",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "where r is any arbitrary real-valued number",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "ZgVJ3CIf2o453TcyRBU1o",
			"type": "arrow",
			"x": -2121.6232716633385,
			"y": -574.0790421081947,
			"width": 401.14283970424106,
			"height": 4.57144601004461,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0i",
			"roundness": {
				"type": 2
			},
			"seed": 636469311,
			"version": 102,
			"versionNonce": 694007217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-401.14283970424106,
					4.57144601004461
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "ZylxnzgR",
			"type": "text",
			"x": -2510.194700234767,
			"y": -616.3647215166768,
			"width": 383.15972900390625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0j",
			"roundness": null,
			"seed": 2141937759,
			"version": 194,
			"versionNonce": 73258897,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "Sequential Active Learning or LocalMax:",
			"rawText": "Sequential Active Learning or LocalMax:",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sequential Active Learning or LocalMax:",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "UOOxzty5",
			"type": "text",
			"x": -2485.051877969142,
			"y": -547.7933801383285,
			"width": 344.519775390625,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0k",
			"roundness": null,
			"seed": 1027472511,
			"version": 209,
			"versionNonce": 851361137,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "Add a query set of unlabeled pixels\nto the current training pixel set\nbased on the acquisition values",
			"rawText": "Add a query set of unlabeled pixels\nto the current training pixel set\nbased on the acquisition values",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Add a query set of unlabeled pixels\nto the current training pixel set\nbased on the acquisition values",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "TCexMhjf7NdoETdgBmkEL",
			"type": "ellipse",
			"x": -2595.6804201880313,
			"y": -562.1059280084769,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0l",
			"roundness": {
				"type": 2
			},
			"seed": 1114117279,
			"version": 251,
			"versionNonce": 331867985,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "zscmXV-vCQXT--_E8EQSI",
			"type": "ellipse",
			"x": -2815.3619740788617,
			"y": -500.89744837815715,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0m",
			"roundness": {
				"type": 2
			},
			"seed": 651831487,
			"version": 237,
			"versionNonce": 835769649,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "fpARaycf3QfeqsHk6uvjF",
					"type": "arrow"
				}
			],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "wIKJaNJc62_J1UWFzAN6x",
			"type": "ellipse",
			"x": -2824.480377463422,
			"y": -652.1059127496878,
			"width": 38.4000244140625,
			"height": 40.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0n",
			"roundness": {
				"type": 2
			},
			"seed": 942979295,
			"version": 333,
			"versionNonce": 428866801,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "9mCzhvzi3C-X6hRcMsCI8",
			"type": "ellipse",
			"x": -2740.480407981,
			"y": -700.5059219049613,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0o",
			"roundness": {
				"type": 2
			},
			"seed": 1007174911,
			"version": 254,
			"versionNonce": 491075281,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "QdHu_9x7XQG-AZWY3mmbW",
			"type": "ellipse",
			"x": -2854.8804018774845,
			"y": -563.7059341119925,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0p",
			"roundness": {
				"type": 2
			},
			"seed": 1909804319,
			"version": 254,
			"versionNonce": 1308112049,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "yW3Rg2fyrcTKROPptfqbK",
			"type": "ellipse",
			"x": -2726.8804323950626,
			"y": -527.7059341119925,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0q",
			"roundness": {
				"type": 2
			},
			"seed": 1426870591,
			"version": 254,
			"versionNonce": 1330673297,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "DENDJUDXsQAZtcM11xfw2",
			"type": "line",
			"x": -2794.0803835669376,
			"y": -651.3059249567191,
			"width": 55.20001220703125,
			"height": 20.800018310546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0r",
			"roundness": {
				"type": 2
			},
			"seed": 520999263,
			"version": 166,
			"versionNonce": 1678081137,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.20001220703125,
					-20.800018310546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "rSpH-T6oYgwluTdD8DThf",
			"type": "line",
			"x": -2818.0804140845157,
			"y": -615.3059249567191,
			"width": 21.5999755859375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0s",
			"roundness": {
				"type": 2
			},
			"seed": 153767295,
			"version": 193,
			"versionNonce": 199149137,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.5999755859375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "QmJaUklDOcYVP_MZOYNTS",
			"type": "line",
			"x": -2800.480407981,
			"y": -492.9059310602347,
			"width": 31.199981689453125,
			"height": 36,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0t",
			"roundness": {
				"type": 2
			},
			"seed": 1319257503,
			"version": 173,
			"versionNonce": 1639175217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-31.199981689453125,
					-36
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "VTtmSn3-qbHu9jztaCTe9",
			"type": "line",
			"x": -2786.8803713599063,
			"y": -497.7059493707816,
			"width": 97.5999755859375,
			"height": 84.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0u",
			"roundness": {
				"type": 2
			},
			"seed": 1856387519,
			"version": 215,
			"versionNonce": 963388945,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					-84.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Wlo9lD1s0jK5Kqoisa-KE",
			"type": "line",
			"x": -2633.280395773969,
			"y": -642.5059371637503,
			"width": 81.5999755859375,
			"height": 29.600006103515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0v",
			"roundness": {
				"type": 2
			},
			"seed": 777431519,
			"version": 197,
			"versionNonce": 2113879025,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-81.5999755859375,
					-29.600006103515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "CO6CSk25IUF1ZNG3S0se4",
			"type": "line",
			"x": -2612.480407981,
			"y": -638.5059371637503,
			"width": 28.79998779296875,
			"height": 78.39999389648438,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0w",
			"roundness": {
				"type": 2
			},
			"seed": 1522800127,
			"version": 193,
			"versionNonce": 1333040593,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.79998779296875,
					78.39999389648438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "fUMhW3Jw8AKMf0eM1J2QJ",
			"type": "line",
			"x": -2690.8803713599063,
			"y": -582.5059371637503,
			"width": 5.60003662109375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0x",
			"roundness": {
				"type": 2
			},
			"seed": 1257176607,
			"version": 187,
			"versionNonce": 1625535409,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.60003662109375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "9vVgVC9vKEGez3pGiPOeF",
			"type": "line",
			"x": -2690.0803835669376,
			"y": -583.3059249567191,
			"width": 97.5999755859375,
			"height": 30.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0y",
			"roundness": {
				"type": 2
			},
			"seed": 566747711,
			"version": 209,
			"versionNonce": 376706449,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					30.399993896484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "l2KdSp9p1ro0HAygrpNoZ",
			"type": "ellipse",
			"x": -2720.6251319735984,
			"y": -627.2132378518415,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b0z",
			"roundness": {
				"type": 2
			},
			"seed": 1345274463,
			"version": 484,
			"versionNonce": 1667054449,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "TpXEWWt5",
			"type": "text",
			"x": -2801.63031032475,
			"y": -492.7434783624808,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b10",
			"roundness": null,
			"seed": 1458937471,
			"version": 229,
			"versionNonce": 1743168849,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "lWypURq1ql50TJzCOfFa1",
			"type": "ellipse",
			"x": -2641.606736184015,
			"y": -680.8373183377089,
			"width": 53.05265727796052,
			"height": 49,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b11",
			"roundness": {
				"type": 2
			},
			"seed": 1222342303,
			"version": 273,
			"versionNonce": 1332204337,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "lvG6x43Y"
				},
				{
					"id": "frBtOMtN9GewGAB1SaObr",
					"type": "arrow"
				}
			],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "lvG6x43Y",
			"type": "text",
			"x": -2625.477353795289,
			"y": -668.6614344767793,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b12",
			"roundness": null,
			"seed": 210848447,
			"version": 37,
			"versionNonce": 1850230033,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "lWypURq1ql50TJzCOfFa1",
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "MglO5Ox8Ff5KB1FwB54S7",
			"type": "freedraw",
			"x": -3013.0246756656943,
			"y": -1205.4420954451707,
			"width": 97.77777777777771,
			"height": 87.11113823784717,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b13",
			"roundness": null,
			"seed": 1589091039,
			"version": 84,
			"versionNonce": 1695872209,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7777506510416288,
					0
				],
				[
					5.333251953125,
					0
				],
				[
					8.8888888888888,
					0
				],
				[
					12.444390190972172,
					0
				],
				[
					16.000027126736086,
					0
				],
				[
					19.555528428819457,
					0
				],
				[
					23.111029730902715,
					0
				],
				[
					26.66666666666663,
					0
				],
				[
					28.444417317708258,
					0
				],
				[
					31.99991861979163,
					0
				],
				[
					35.55555555555554,
					0
				],
				[
					39.1110568576388,
					0
				],
				[
					40.88880750868054,
					0
				],
				[
					44.44444444444434,
					-1.777818467881957
				],
				[
					46.222195095486086,
					-1.777818467881957
				],
				[
					49.77769639756934,
					-1.777818467881957
				],
				[
					53.33333333333326,
					-1.777818467881957
				],
				[
					55.111083984375,
					-1.777818467881957
				],
				[
					58.66658528645826,
					-1.777818467881957
				],
				[
					60.44447157118054,
					-1.777818467881957
				],
				[
					62.22222222222217,
					-1.777818467881957
				],
				[
					63.9999728732638,
					-1.777818467881957
				],
				[
					65.77772352430554,
					-1.777818467881957
				],
				[
					67.55547417534717,
					-1.777818467881957
				],
				[
					69.33336046006934,
					-1.777818467881957
				],
				[
					71.11111111111109,
					-1.777818467881957
				],
				[
					74.66661241319434,
					-1.777818467881957
				],
				[
					80,
					-1.777818467881957
				],
				[
					88.8888888888888,
					-1.777818467881957
				],
				[
					92.44439019097217,
					-1.777818467881957
				],
				[
					94.2221408420138,
					-1.777818467881957
				],
				[
					96.00002712673609,
					-1.777818467881957
				],
				[
					97.77777777777771,
					-1.777818467881957
				],
				[
					97.77777777777771,
					1.7777506510416288
				],
				[
					97.77777777777771,
					7.111070421006957
				],
				[
					97.77777777777771,
					14.222208658854129
				],
				[
					97.77777777777771,
					21.333279079861086
				],
				[
					97.77777777777771,
					28.444417317708314
				],
				[
					97.77777777777771,
					35.55555555555554
				],
				[
					97.77777777777771,
					44.44444444444446
				],
				[
					97.77777777777771,
					51.55551486545136
				],
				[
					97.77777777777771,
					60.44440375434027
				],
				[
					97.77777777777771,
					65.77772352430554
				],
				[
					97.77777777777771,
					71.11111111111109
				],
				[
					97.77777777777771,
					72.88886176215271
				],
				[
					97.77777777777771,
					76.44443088107641
				],
				[
					97.77777777777771,
					78.22218153211804
				],
				[
					97.77777777777771,
					80
				],
				[
					97.77777777777771,
					81.77775065104163
				],
				[
					97.77777777777771,
					83.55550130208337
				],
				[
					97.77777777777771,
					85.33331976996521
				],
				[
					97.77777777777771,
					85.33331976996521
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "0KN6axrt",
			"type": "text",
			"x": -3301.0247570459023,
			"y": -881.8865263262473,
			"width": 348.59979248046875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b14",
			"roundness": null,
			"seed": 333375231,
			"version": 159,
			"versionNonce": 1092629169,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "Repeat until the desired number of \ntraining pixels is reached",
			"rawText": "Repeat until the desired number of \ntraining pixels is reached",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Repeat until the desired number of \ntraining pixels is reached",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "2mQ0iw1hSY91NsuVWMhOI",
			"type": "freedraw",
			"x": -3338.3580632525,
			"y": -787.6643854842332,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b15",
			"roundness": null,
			"seed": 445099807,
			"version": 32,
			"versionNonce": 1489548433,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "39bTUJkTWG0kv_stPGmyE",
			"type": "freedraw",
			"x": -3343.691315205625,
			"y": -849.8866077064554,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b16",
			"roundness": null,
			"seed": 1025667903,
			"version": 32,
			"versionNonce": 1338374769,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "xSnyvx1fzLQYSqR7LeiL3",
			"type": "freedraw",
			"x": -3333.0246756656943,
			"y": -915.664331230761,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b17",
			"roundness": null,
			"seed": 605008735,
			"version": 32,
			"versionNonce": 1725924433,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "yD771n9Ry82Hpzy5HyPu_",
			"type": "freedraw",
			"x": -3311.691396585833,
			"y": -965.4420954451707,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b18",
			"roundness": null,
			"seed": 396357503,
			"version": 32,
			"versionNonce": 1508692529,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "BTiFIJeCA76xRv9mZSPwr",
			"type": "freedraw",
			"x": -3281.4690929834023,
			"y": -1008.1087892385735,
			"width": 355.55555555555554,
			"height": 188.44441731770837,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b19",
			"roundness": null,
			"seed": 34842527,
			"version": 163,
			"versionNonce": 2111136785,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.5555013020833712,
					0
				],
				[
					5.333251953125,
					-1.7777506510417425
				],
				[
					8.888888888888914,
					-3.5555691189236995
				],
				[
					10.666639539930543,
					-7.111138237847285
				],
				[
					14.222140842013914,
					-8.888888888888914
				],
				[
					17.777777777777715,
					-10.666639539930543
				],
				[
					19.555528428819457,
					-12.4444580078125
				],
				[
					23.111029730902715,
					-14.222208658854242
				],
				[
					26.66666666666663,
					-16.0000271267362
				],
				[
					30.22216796875,
					-17.77777777777783
				],
				[
					35.55555555555554,
					-19.555528428819457
				],
				[
					40.88880750868054,
					-21.333346896701414
				],
				[
					46.222195095486086,
					-23.111097547743043
				],
				[
					49.77769639756946,
					-24.888916015625
				],
				[
					55.111083984375,
					-26.666666666666742
				],
				[
					58.66658528645837,
					-26.666666666666742
				],
				[
					63.999972873263914,
					-28.44441731770837
				],
				[
					67.55547417534717,
					-30.22223578559033
				],
				[
					71.11111111111109,
					-30.22223578559033
				],
				[
					74.66661241319446,
					-30.22223578559033
				],
				[
					76.44436306423609,
					-31.999986436631957
				],
				[
					80,
					-33.777804904513914
				],
				[
					83.55550130208337,
					-33.777804904513914
				],
				[
					88.88888888888891,
					-35.55555555555554
				],
				[
					90.66663953993054,
					-35.55555555555554
				],
				[
					94.22214084201391,
					-37.333306206597285
				],
				[
					97.77777777777783,
					-39.11112467447924
				],
				[
					99.55552842881946,
					-39.11112467447924
				],
				[
					103.11102973090283,
					-40.88887532552087
				],
				[
					104.88878038194446,
					-40.88887532552087
				],
				[
					108.44441731770837,
					-42.66669379340283
				],
				[
					110.22216796875,
					-42.66669379340283
				],
				[
					111.99991861979163,
					-42.66669379340283
				],
				[
					113.77766927083337,
					-44.44444444444446
				],
				[
					119.11105685763891,
					-46.2221950954862
				],
				[
					122.66655815972217,
					-48.00001356336804
				],
				[
					124.44444444444446,
					-48.00001356336804
				],
				[
					127.99994574652783,
					-49.777764214409785
				],
				[
					131.5554470486111,
					-51.55558268229174
				],
				[
					136.88883463541663,
					-51.55558268229174
				],
				[
					140.4443359375,
					-53.33333333333337
				],
				[
					145.77772352430554,
					-56.88890245225696
				],
				[
					149.3332248263889,
					-56.88890245225696
				],
				[
					152.88886176215283,
					-60.44447157118054
				],
				[
					156.4443630642361,
					-60.44447157118054
				],
				[
					160,
					-62.222222222222285
				],
				[
					163.55550130208337,
					-65.77779134114587
				],
				[
					167.11100260416663,
					-65.77779134114587
				],
				[
					170.66663953993054,
					-67.5555419921875
				],
				[
					172.44439019097217,
					-69.33336046006946
				],
				[
					175.99989149305554,
					-69.33336046006946
				],
				[
					177.77777777777783,
					-71.1111111111112
				],
				[
					179.55552842881946,
					-71.1111111111112
				],
				[
					181.3332790798611,
					-72.88886176215283
				],
				[
					184.88878038194446,
					-72.88886176215283
				],
				[
					184.88878038194446,
					-74.66668023003479
				],
				[
					186.66666666666663,
					-74.66668023003479
				],
				[
					188.44441731770837,
					-74.66668023003479
				],
				[
					190.22216796875,
					-76.44443088107641
				],
				[
					193.77766927083337,
					-76.44443088107641
				],
				[
					193.77766927083337,
					-78.22224934895837
				],
				[
					195.55555555555554,
					-78.22224934895837
				],
				[
					197.33330620659717,
					-78.22224934895837
				],
				[
					199.1110568576389,
					-80
				],
				[
					202.66655815972217,
					-81.77775065104174
				],
				[
					204.44444444444446,
					-83.5555691189237
				],
				[
					207.99994574652783,
					-83.5555691189237
				],
				[
					213.33333333333337,
					-87.11113823784729
				],
				[
					216.88883463541663,
					-90.66663953993054
				],
				[
					220.4443359375,
					-90.66663953993054
				],
				[
					223.9999728732639,
					-94.22220865885424
				],
				[
					227.55547417534717,
					-96.0000271267362
				],
				[
					232.88886176215283,
					-97.77777777777783
				],
				[
					234.66661241319446,
					-99.55552842881946
				],
				[
					236.4443630642361,
					-101.33334689670141
				],
				[
					241.77775065104163,
					-103.11109754774304
				],
				[
					245.333251953125,
					-104.888916015625
				],
				[
					248.8888888888889,
					-108.44441731770837
				],
				[
					254.2221408420139,
					-111.99998643663196
				],
				[
					259.55552842881946,
					-113.77780490451391
				],
				[
					263.1110297309028,
					-117.33330620659729
				],
				[
					266.66666666666663,
					-117.33330620659729
				],
				[
					268.44441731770837,
					-119.11112467447924
				],
				[
					271.99991861979163,
					-122.66669379340283
				],
				[
					273.77766927083337,
					-122.66669379340283
				],
				[
					275.55555555555554,
					-124.44444444444446
				],
				[
					279.1110568576389,
					-126.22219509548609
				],
				[
					280.88880750868054,
					-128.00001356336804
				],
				[
					282.6665581597222,
					-131.55558268229174
				],
				[
					284.44444444444446,
					-131.55558268229174
				],
				[
					287.9999457465278,
					-133.33333333333337
				],
				[
					289.77769639756946,
					-135.111083984375
				],
				[
					293.33333333333337,
					-136.88890245225696
				],
				[
					293.33333333333337,
					-138.6666531032986
				],
				[
					295.111083984375,
					-138.6666531032986
				],
				[
					296.88883463541663,
					-140.44447157118054
				],
				[
					298.66658528645837,
					-140.44447157118054
				],
				[
					298.66658528645837,
					-142.22222222222229
				],
				[
					300.4443359375,
					-143.9999728732639
				],
				[
					302.2222222222222,
					-143.9999728732639
				],
				[
					303.9999728732639,
					-145.77779134114587
				],
				[
					307.5554741753472,
					-147.5555419921875
				],
				[
					309.3332248263889,
					-149.33336046006946
				],
				[
					311.1111111111111,
					-151.1111111111111
				],
				[
					311.1111111111111,
					-152.88886176215283
				],
				[
					312.8888617621527,
					-152.88886176215283
				],
				[
					314.66661241319446,
					-154.66668023003479
				],
				[
					316.4443630642361,
					-154.66668023003479
				],
				[
					316.4443630642361,
					-156.4444308810764
				],
				[
					320,
					-156.4444308810764
				],
				[
					320,
					-158.22224934895837
				],
				[
					321.77775065104163,
					-160
				],
				[
					323.55550130208337,
					-161.77775065104174
				],
				[
					325.333251953125,
					-161.77775065104174
				],
				[
					327.11100260416663,
					-163.5555691189236
				],
				[
					328.8888888888889,
					-165.33331976996533
				],
				[
					330.66663953993054,
					-167.11113823784729
				],
				[
					332.4443901909722,
					-168.8888888888889
				],
				[
					332.4443901909722,
					-170.66663953993054
				],
				[
					334.2221408420139,
					-170.66663953993054
				],
				[
					335.99989149305554,
					-172.4444580078125
				],
				[
					337.7777777777777,
					-172.4444580078125
				],
				[
					337.7777777777777,
					-174.22220865885424
				],
				[
					339.55552842881946,
					-174.22220865885424
				],
				[
					341.3332790798611,
					-176.0000271267361
				],
				[
					350.22216796875,
					-183.11109754774304
				],
				[
					351.99991861979163,
					-184.888916015625
				],
				[
					351.99991861979163,
					-186.66666666666674
				],
				[
					353.77766927083337,
					-186.66666666666674
				],
				[
					355.55555555555554,
					-186.66666666666674
				],
				[
					355.55555555555554,
					-188.44441731770837
				],
				[
					355.55555555555554,
					-188.44441731770837
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "-XBB1tcyZfiVeeH7PZqku",
			"type": "rectangle",
			"x": -2998.8025348236806,
			"y": -1013.4421090085384,
			"width": 257.7777777777778,
			"height": 106.66659884982641,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 40,
			"groupIds": [
				"OjnfT8i41qOnh3K8xIQLr",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1A",
			"roundness": {
				"type": 3
			},
			"seed": 832265151,
			"version": 285,
			"versionNonce": 512801265,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "frBtOMtN9GewGAB1SaObr",
					"type": "arrow"
				}
			],
			"updated": 1735665508772,
			"link": null,
			"locked": false
		},
		{
			"id": "7OcDiOhV",
			"type": "text",
			"x": -2958.1080569111855,
			"y": -1001.8361604984302,
			"width": 188.3199005126953,
			"height": 75,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"OjnfT8i41qOnh3K8xIQLr",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1B",
			"roundness": null,
			"seed": 1515686879,
			"version": 305,
			"versionNonce": 1303228849,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "The current set of\ntraining pixels\n(labeled pixel)",
			"rawText": "The current set of\ntraining pixels\n(labeled pixel)",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The current set of\ntraining pixels\n(labeled pixel)",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "frBtOMtN9GewGAB1SaObr",
			"type": "arrow",
			"x": -2844.1357867768056,
			"y": -892.5531658661776,
			"width": 218.6679965186686,
			"height": 202.66786613082616,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1C",
			"roundness": {
				"type": 2
			},
			"seed": 1482209279,
			"version": 199,
			"versionNonce": 1185946367,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508929,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					218.6679965186686,
					202.66786613082616
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "-XBB1tcyZfiVeeH7PZqku",
				"focus": 0.2526977904449714,
				"gap": 14.222344292534444,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "lWypURq1ql50TJzCOfFa1",
				"focus": 0.6891841223819251,
				"gap": 10.453543689863437,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "fpARaycf3QfeqsHk6uvjF",
			"type": "arrow",
			"x": -2851.2469250146523,
			"y": -878.3310250241639,
			"width": 60.44447157118054,
			"height": 368.00008138020837,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1D",
			"roundness": {
				"type": 2
			},
			"seed": 832528415,
			"version": 162,
			"versionNonce": 1158832927,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508929,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					60.44447157118054,
					368.00008138020837
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "zscmXV-vCQXT--_E8EQSI",
				"focus": 0.12383231659745074,
				"gap": 9.481372807884341,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "J77kkGYV",
			"type": "text",
			"x": -4401.407751678292,
			"y": -1263.7859892021565,
			"width": 76.33064270019531,
			"height": 39.53358365815827,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1E",
			"roundness": null,
			"seed": 1478231103,
			"version": 505,
			"versionNonce": 1204380497,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q* = ",
			"rawText": "q* = ",
			"fontSize": 31.626866926526617,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q* = ",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "JJVw7IYd",
			"type": "text",
			"x": -4138.176891677577,
			"y": -561.3024870706788,
			"width": 76.33064270019531,
			"height": 39.53358365815827,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1F",
			"roundness": null,
			"seed": 732898399,
			"version": 618,
			"versionNonce": 1614991665,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q* = ",
			"rawText": "q* = ",
			"fontSize": 31.626866926526617,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q* = ",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "5q0uBhjH",
			"type": "text",
			"x": -4154.949271019473,
			"y": -1261.882388692747,
			"width": 76.33064270019531,
			"height": 39.53358365815827,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1G",
			"roundness": null,
			"seed": 1009336447,
			"version": 578,
			"versionNonce": 1729331985,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q* = ",
			"rawText": "q* = ",
			"fontSize": 31.626866926526617,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q* = ",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "9lJEr5X6",
			"type": "text",
			"x": -3828.7640807837015,
			"y": -1268.9368439033428,
			"width": 76.33064270019531,
			"height": 39.53358365815827,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1H",
			"roundness": null,
			"seed": 1263196319,
			"version": 678,
			"versionNonce": 414382321,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"text": "q* = ",
			"rawText": "q* = ",
			"fontSize": 31.626866926526617,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q* = ",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "ra3hI6G6ghLsB8XAGClC7",
			"type": "line",
			"x": -4318.720018645533,
			"y": -1337.385237777784,
			"width": 25.08258335383044,
			"height": 0,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1I",
			"roundness": {
				"type": 2
			},
			"seed": 247753919,
			"version": 474,
			"versionNonce": 917025489,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					25.08258335383044,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "FJ6v25_ol4hLmM2Lplywr",
			"type": "line",
			"x": -4055.4891586448193,
			"y": -634.9017356463064,
			"width": 25.08258335383044,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1J",
			"roundness": {
				"type": 2
			},
			"seed": 842431711,
			"version": 587,
			"versionNonce": 1703686321,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					25.08258335383044,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "QECwbY4AMaVzD2Atq7zd5",
			"type": "line",
			"x": -4072.2615379867148,
			"y": -1335.481637268375,
			"width": 25.08258335383044,
			"height": 0,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1K",
			"roundness": {
				"type": 2
			},
			"seed": 422676735,
			"version": 547,
			"versionNonce": 1258615441,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					25.08258335383044,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "gCm3MHhBe4ubPfHLbX_Xr",
			"type": "line",
			"x": -3746.0763477509427,
			"y": -1342.5360924789702,
			"width": 25.08258335383044,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1L",
			"roundness": {
				"type": 2
			},
			"seed": 1630933279,
			"version": 680,
			"versionNonce": 1808431217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					25.08258335383044,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "sPFS3BhRZve3TQrI-Ixoy",
			"type": "line",
			"x": -4314.240990785531,
			"y": -1334.6977937239658,
			"width": 1.7916521507257277,
			"height": 194.38978178629048,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1M",
			"roundness": {
				"type": 2
			},
			"seed": 599037247,
			"version": 628,
			"versionNonce": 1235501649,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7916521507257277,
					194.38978178629048
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "h_a-5ipNZuOMxEtIYv6qG",
			"type": "line",
			"x": -4051.0101307848163,
			"y": -632.2142915924883,
			"width": 1.7916521507257277,
			"height": 194.38978178629048,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1N",
			"roundness": {
				"type": 2
			},
			"seed": 2014156127,
			"version": 743,
			"versionNonce": 1097453617,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7916521507257277,
					194.38978178629048
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "fAJ7g0szXVR7nSw2P5_AE",
			"type": "line",
			"x": -4067.7825101267117,
			"y": -1332.7941932145568,
			"width": 1.7916521507257277,
			"height": 194.38978178629048,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1O",
			"roundness": {
				"type": 2
			},
			"seed": 898732415,
			"version": 701,
			"versionNonce": 688038417,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7916521507257277,
					194.38978178629048
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "UnWacNA9D9qRavNOmEu5e",
			"type": "line",
			"x": -3741.5973198909405,
			"y": -1339.848648425152,
			"width": 1.7916521507257277,
			"height": 194.38978178629048,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1P",
			"roundness": {
				"type": 2
			},
			"seed": 1971390879,
			"version": 801,
			"versionNonce": 761673713,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.7916521507257277,
					194.38978178629048
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "zQWi9-Jp-1yMbeudFELjW",
			"type": "line",
			"x": -4314.240990785531,
			"y": -1138.5163597869496,
			"width": 12.54129167691522,
			"height": 0,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1Q",
			"roundness": {
				"type": 2
			},
			"seed": 1426881983,
			"version": 455,
			"versionNonce": 1889276369,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					12.54129167691522,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "BhI_eKIylCwFZUgmnKw4-",
			"type": "line",
			"x": -4051.0101307848163,
			"y": -436.03285765547207,
			"width": 12.54129167691522,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1R",
			"roundness": {
				"type": 2
			},
			"seed": 2002021855,
			"version": 568,
			"versionNonce": 1740353457,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					12.54129167691522,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "YP18eFAw_HRpd3lu7l5mX",
			"type": "line",
			"x": -4067.7825101267117,
			"y": -1136.6127592775406,
			"width": 12.54129167691522,
			"height": 0,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1S",
			"roundness": {
				"type": 2
			},
			"seed": 1198086655,
			"version": 528,
			"versionNonce": 2028769681,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					12.54129167691522,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "BhusZgpnTF-tFQXIJHtJ2",
			"type": "line",
			"x": -3741.5973198909405,
			"y": -1143.6672144881363,
			"width": 12.54129167691522,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1T",
			"roundness": {
				"type": 2
			},
			"seed": 2051785247,
			"version": 628,
			"versionNonce": 1499871089,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					12.54129167691522,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "40t51Re3IpExXMZNkD6iE",
			"type": "freedraw",
			"x": -4265.867476228596,
			"y": -1332.9062099177813,
			"width": 17.9161114400098,
			"height": 25.082515009289054,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1U",
			"roundness": null,
			"seed": 1357653567,
			"version": 527,
			"versionNonce": 728768849,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8957919030922544,
					0
				],
				[
					-0.8957919030922544,
					-0.8957919030922544
				],
				[
					-2.6873757092765977,
					-1.791583806184426
				],
				[
					-3.583235956910237,
					-1.791583806184426
				],
				[
					-4.479027860002492,
					-1.791583806184426
				],
				[
					-5.374819763094581,
					-1.791583806184426
				],
				[
					-6.270611666186834,
					-1.791583806184426
				],
				[
					-7.1664035692790895,
					-1.791583806184426
				],
				[
					-8.06226381691273,
					-1.791583806184426
				],
				[
					-8.958055720004818,
					-1.791583806184426
				],
				[
					-9.853847623097073,
					-1.791583806184426
				],
				[
					-10.749639526189325,
					-0.8957919030922544
				],
				[
					-11.645431429281414,
					0
				],
				[
					-11.645431429281414,
					0.8957919030922544
				],
				[
					-11.645431429281414,
					1.7916521507258105
				],
				[
					-12.541291676915053,
					2.6874440538179827
				],
				[
					-12.541291676915053,
					5.374819763094746
				],
				[
					-13.43708358000731,
					6.27068001072822
				],
				[
					-13.43708358000731,
					8.958055720004984
				],
				[
					-13.43708358000731,
					9.853847623097156
				],
				[
					-13.43708358000731,
					10.74970787073071
				],
				[
					-13.43708358000731,
					11.645499773822966
				],
				[
					-13.43708358000731,
					13.437083580007391
				],
				[
					-13.43708358000731,
					14.332875483099645
				],
				[
					-13.43708358000731,
					15.228735730733202
				],
				[
					-13.43708358000731,
					16.12452763382546
				],
				[
					-13.43708358000731,
					17.02031953691763
				],
				[
					-12.541291676915053,
					17.916111440009885
				],
				[
					-12.541291676915053,
					18.811903343102138
				],
				[
					-12.541291676915053,
					19.707763590735695
				],
				[
					-12.541291676915053,
					20.603555493827866
				],
				[
					-11.645431429281414,
					20.603555493827866
				],
				[
					-10.749639526189325,
					20.603555493827866
				],
				[
					-9.853847623097073,
					21.499347396920122
				],
				[
					-8.958055720004818,
					21.499347396920122
				],
				[
					-8.06226381691273,
					21.499347396920122
				],
				[
					-9.853847623097073,
					22.395139300012374
				],
				[
					-11.645431429281414,
					22.395139300012374
				],
				[
					-12.541291676915053,
					22.395139300012374
				],
				[
					-11.645431429281414,
					21.499347396920122
				],
				[
					-10.749639526189325,
					20.603555493827866
				],
				[
					-9.853847623097073,
					20.603555493827866
				],
				[
					-8.958055720004818,
					19.707763590735695
				],
				[
					-8.06226381691273,
					19.707763590735695
				],
				[
					-7.1664035692790895,
					19.707763590735695
				],
				[
					-7.1664035692790895,
					18.811903343102138
				],
				[
					-6.270611666186834,
					18.811903343102138
				],
				[
					-5.374819763094581,
					17.916111440009885
				],
				[
					-4.479027860002492,
					17.02031953691763
				],
				[
					-3.583235956910237,
					17.02031953691763
				],
				[
					-2.6873757092765977,
					17.02031953691763
				],
				[
					-1.7915838061843437,
					17.02031953691763
				],
				[
					-0.8957919030922544,
					17.02031953691763
				],
				[
					0,
					17.02031953691763
				],
				[
					0,
					16.12452763382546
				],
				[
					0.8957919030922544,
					16.12452763382546
				],
				[
					1.7916521507258936,
					14.332875483099645
				],
				[
					1.7916521507258936,
					13.437083580007391
				],
				[
					2.6874440538179827,
					13.437083580007391
				],
				[
					2.6874440538179827,
					12.54129167691522
				],
				[
					2.6874440538179827,
					11.645499773822966
				],
				[
					3.583235956910237,
					11.645499773822966
				],
				[
					3.583235956910237,
					9.853847623097156
				],
				[
					3.583235956910237,
					8.06226381691273
				],
				[
					3.583235956910237,
					7.166471913820474
				],
				[
					4.479027860002492,
					6.27068001072822
				],
				[
					4.479027860002492,
					5.374819763094746
				],
				[
					4.479027860002492,
					4.479027860002492
				],
				[
					4.479027860002492,
					2.6874440538179827
				],
				[
					4.479027860002492,
					0.8957919030922544
				],
				[
					4.479027860002492,
					0
				],
				[
					4.479027860002492,
					-0.8957919030922544
				],
				[
					4.479027860002492,
					-1.791583806184426
				],
				[
					3.583235956910237,
					-1.791583806184426
				],
				[
					2.6874440538179827,
					-1.791583806184426
				],
				[
					1.7916521507258936,
					-2.6873757092766803
				],
				[
					0.8957919030922544,
					-2.6873757092766803
				],
				[
					0,
					-2.6873757092766803
				],
				[
					0,
					-2.6873757092766803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "mLNiYSQO_w9jcUEY9Yzkj",
			"type": "freedraw",
			"x": -4019.4089955697764,
			"y": -1331.0026094083719,
			"width": 17.9161114400098,
			"height": 25.082515009289054,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1V",
			"roundness": null,
			"seed": 439027295,
			"version": 600,
			"versionNonce": 1549913905,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8957919030922544,
					0
				],
				[
					-0.8957919030922544,
					-0.8957919030922544
				],
				[
					-2.6873757092765977,
					-1.791583806184426
				],
				[
					-3.583235956910237,
					-1.791583806184426
				],
				[
					-4.479027860002492,
					-1.791583806184426
				],
				[
					-5.374819763094581,
					-1.791583806184426
				],
				[
					-6.270611666186834,
					-1.791583806184426
				],
				[
					-7.1664035692790895,
					-1.791583806184426
				],
				[
					-8.06226381691273,
					-1.791583806184426
				],
				[
					-8.958055720004818,
					-1.791583806184426
				],
				[
					-9.853847623097073,
					-1.791583806184426
				],
				[
					-10.749639526189325,
					-0.8957919030922544
				],
				[
					-11.645431429281414,
					0
				],
				[
					-11.645431429281414,
					0.8957919030922544
				],
				[
					-11.645431429281414,
					1.7916521507258105
				],
				[
					-12.541291676915053,
					2.6874440538179827
				],
				[
					-12.541291676915053,
					5.374819763094746
				],
				[
					-13.43708358000731,
					6.27068001072822
				],
				[
					-13.43708358000731,
					8.958055720004984
				],
				[
					-13.43708358000731,
					9.853847623097156
				],
				[
					-13.43708358000731,
					10.74970787073071
				],
				[
					-13.43708358000731,
					11.645499773822966
				],
				[
					-13.43708358000731,
					13.437083580007391
				],
				[
					-13.43708358000731,
					14.332875483099645
				],
				[
					-13.43708358000731,
					15.228735730733202
				],
				[
					-13.43708358000731,
					16.12452763382546
				],
				[
					-13.43708358000731,
					17.02031953691763
				],
				[
					-12.541291676915053,
					17.916111440009885
				],
				[
					-12.541291676915053,
					18.811903343102138
				],
				[
					-12.541291676915053,
					19.707763590735695
				],
				[
					-12.541291676915053,
					20.603555493827866
				],
				[
					-11.645431429281414,
					20.603555493827866
				],
				[
					-10.749639526189325,
					20.603555493827866
				],
				[
					-9.853847623097073,
					21.499347396920122
				],
				[
					-8.958055720004818,
					21.499347396920122
				],
				[
					-8.06226381691273,
					21.499347396920122
				],
				[
					-9.853847623097073,
					22.395139300012374
				],
				[
					-11.645431429281414,
					22.395139300012374
				],
				[
					-12.541291676915053,
					22.395139300012374
				],
				[
					-11.645431429281414,
					21.499347396920122
				],
				[
					-10.749639526189325,
					20.603555493827866
				],
				[
					-9.853847623097073,
					20.603555493827866
				],
				[
					-8.958055720004818,
					19.707763590735695
				],
				[
					-8.06226381691273,
					19.707763590735695
				],
				[
					-7.1664035692790895,
					19.707763590735695
				],
				[
					-7.1664035692790895,
					18.811903343102138
				],
				[
					-6.270611666186834,
					18.811903343102138
				],
				[
					-5.374819763094581,
					17.916111440009885
				],
				[
					-4.479027860002492,
					17.02031953691763
				],
				[
					-3.583235956910237,
					17.02031953691763
				],
				[
					-2.6873757092765977,
					17.02031953691763
				],
				[
					-1.7915838061843437,
					17.02031953691763
				],
				[
					-0.8957919030922544,
					17.02031953691763
				],
				[
					0,
					17.02031953691763
				],
				[
					0,
					16.12452763382546
				],
				[
					0.8957919030922544,
					16.12452763382546
				],
				[
					1.7916521507258936,
					14.332875483099645
				],
				[
					1.7916521507258936,
					13.437083580007391
				],
				[
					2.6874440538179827,
					13.437083580007391
				],
				[
					2.6874440538179827,
					12.54129167691522
				],
				[
					2.6874440538179827,
					11.645499773822966
				],
				[
					3.583235956910237,
					11.645499773822966
				],
				[
					3.583235956910237,
					9.853847623097156
				],
				[
					3.583235956910237,
					8.06226381691273
				],
				[
					3.583235956910237,
					7.166471913820474
				],
				[
					4.479027860002492,
					6.27068001072822
				],
				[
					4.479027860002492,
					5.374819763094746
				],
				[
					4.479027860002492,
					4.479027860002492
				],
				[
					4.479027860002492,
					2.6874440538179827
				],
				[
					4.479027860002492,
					0.8957919030922544
				],
				[
					4.479027860002492,
					0
				],
				[
					4.479027860002492,
					-0.8957919030922544
				],
				[
					4.479027860002492,
					-1.791583806184426
				],
				[
					3.583235956910237,
					-1.791583806184426
				],
				[
					2.6874440538179827,
					-1.791583806184426
				],
				[
					1.7916521507258936,
					-2.6873757092766803
				],
				[
					0.8957919030922544,
					-2.6873757092766803
				],
				[
					0,
					-2.6873757092766803
				],
				[
					0,
					-2.6873757092766803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "BoIH5KhjvrSQLokG23NGL",
			"type": "freedraw",
			"x": -4264.971684325504,
			"y": -1284.5326953608464,
			"width": 18.811971687643275,
			"height": 35.83222288001977,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1W",
			"roundness": null,
			"seed": 1960370815,
			"version": 541,
			"versionNonce": 1117962513,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8957919030922544,
					0
				],
				[
					-1.7915838061845089,
					0
				],
				[
					-2.6873757092765977,
					0
				],
				[
					-3.583167612368852,
					0
				],
				[
					-4.479027860002492,
					0
				],
				[
					-4.479027860002492,
					0.8957919030922546
				],
				[
					-5.374819763094746,
					0.8957919030922546
				],
				[
					-5.374819763094746,
					1.7915838061844267
				],
				[
					-6.270611666186834,
					1.7915838061844267
				],
				[
					-8.062195472371345,
					3.5832359569102374
				],
				[
					-8.958055720004984,
					4.479027860002493
				],
				[
					-9.853847623097073,
					6.270611666186919
				],
				[
					-10.749639526189325,
					6.270611666186919
				],
				[
					-10.749639526189325,
					7.166471913820475
				],
				[
					-10.749639526189325,
					8.062263816912731
				],
				[
					-10.749639526189325,
					8.958055720004902
				],
				[
					-11.64543142928158,
					9.853847623097156
				],
				[
					-11.64543142928158,
					10.749639526189412
				],
				[
					-12.541223332373669,
					10.749639526189412
				],
				[
					-12.541223332373669,
					11.645499773822968
				],
				[
					-12.541223332373669,
					13.437083580007394
				],
				[
					-13.43708358000731,
					13.437083580007394
				],
				[
					-13.43708358000731,
					15.228667386191903
				],
				[
					-13.43708358000731,
					17.02031953691763
				],
				[
					-13.43708358000731,
					17.916111440009885
				],
				[
					-13.43708358000731,
					18.81190334310214
				],
				[
					-13.43708358000731,
					19.707695246194312
				],
				[
					-13.43708358000731,
					20.603555493827873
				],
				[
					-13.43708358000731,
					21.499347396920125
				],
				[
					-13.43708358000731,
					22.395139300012296
				],
				[
					-13.43708358000731,
					23.290931203104552
				],
				[
					-12.541223332373669,
					24.186723106196805
				],
				[
					-12.541223332373669,
					25.082583353830362
				],
				[
					-11.64543142928158,
					25.978375256922533
				],
				[
					-11.64543142928158,
					26.87416716001479
				],
				[
					-11.64543142928158,
					27.76995906310705
				],
				[
					-11.64543142928158,
					28.665750966199298
				],
				[
					-10.749639526189325,
					28.665750966199298
				],
				[
					-10.749639526189325,
					29.561611213832776
				],
				[
					-10.749639526189325,
					30.457403116925025
				],
				[
					-9.853847623097073,
					30.457403116925025
				],
				[
					-9.853847623097073,
					31.353195020017285
				],
				[
					-9.853847623097073,
					32.248986923109534
				],
				[
					-8.958055720004984,
					33.14477882620171
				],
				[
					-8.062195472371345,
					33.14477882620171
				],
				[
					-7.1664035692790895,
					34.04063907383526
				],
				[
					-7.1664035692790895,
					34.936430976927525
				],
				[
					-6.270611666186834,
					34.936430976927525
				],
				[
					-5.374819763094746,
					34.936430976927525
				],
				[
					-4.479027860002492,
					34.936430976927525
				],
				[
					-3.583167612368852,
					35.83222288001977
				],
				[
					-2.6873757092765977,
					35.83222288001977
				],
				[
					-1.7915838061845089,
					35.83222288001977
				],
				[
					-0.8957919030922544,
					35.83222288001977
				],
				[
					-0.8957919030922544,
					34.936430976927525
				],
				[
					-0.8957919030922544,
					34.04063907383526
				],
				[
					0,
					33.14477882620171
				],
				[
					0.895860247633639,
					32.248986923109534
				],
				[
					0.895860247633639,
					31.353195020017285
				],
				[
					0.895860247633639,
					29.561611213832776
				],
				[
					1.7916521507257277,
					29.561611213832776
				],
				[
					1.7916521507257277,
					28.665750966199298
				],
				[
					2.6874440538179827,
					27.76995906310705
				],
				[
					2.6874440538179827,
					26.87416716001479
				],
				[
					3.583235956910237,
					26.87416716001479
				],
				[
					3.583235956910237,
					25.082583353830362
				],
				[
					3.583235956910237,
					24.186723106196805
				],
				[
					3.583235956910237,
					23.290931203104552
				],
				[
					3.583235956910237,
					22.395139300012296
				],
				[
					4.479027860002492,
					21.499347396920125
				],
				[
					4.479027860002492,
					20.603555493827873
				],
				[
					4.479027860002492,
					19.707695246194312
				],
				[
					5.374888107635965,
					18.81190334310214
				],
				[
					5.374888107635965,
					17.02031953691763
				],
				[
					5.374888107635965,
					16.124527633825377
				],
				[
					5.374888107635965,
					15.228667386191903
				],
				[
					5.374888107635965,
					14.332875483099649
				],
				[
					5.374888107635965,
					13.437083580007394
				],
				[
					5.374888107635965,
					11.645499773822968
				],
				[
					5.374888107635965,
					10.749639526189412
				],
				[
					5.374888107635965,
					9.853847623097156
				],
				[
					5.374888107635965,
					8.062263816912731
				],
				[
					4.479027860002492,
					7.166471913820475
				],
				[
					4.479027860002492,
					5.374819763094664
				],
				[
					4.479027860002492,
					4.479027860002493
				],
				[
					4.479027860002492,
					3.5832359569102374
				],
				[
					3.583235956910237,
					3.5832359569102374
				],
				[
					3.583235956910237,
					2.687444053817983
				],
				[
					2.6874440538179827,
					2.687444053817983
				],
				[
					1.7916521507257277,
					1.7915838061844267
				],
				[
					1.7916521507257277,
					0.8957919030922546
				],
				[
					0.895860247633639,
					0.8957919030922546
				],
				[
					0.895860247633639,
					0.8957919030922546
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "H8CJgaiG9WR8uOGpYVTYE",
			"type": "freedraw",
			"x": -4266.763268131688,
			"y": -1234.367596997727,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1X",
			"roundness": null,
			"seed": 1370897055,
			"version": 449,
			"versionNonce": 2074769137,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "iALl9KEdbeRf7WDYTlR19",
			"type": "freedraw",
			"x": -4020.304787472869,
			"y": -1232.4639964883181,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1Y",
			"roundness": null,
			"seed": 896765631,
			"version": 522,
			"versionNonce": 167801041,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "haKtCr_eIkyQFVQnuvN8R",
			"type": "freedraw",
			"x": -3694.119597237098,
			"y": -1239.5184516989134,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1Z",
			"roundness": null,
			"seed": 984702687,
			"version": 622,
			"versionNonce": 859582129,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "d78uJRnUhTAGrF5RDwrCO",
			"type": "freedraw",
			"x": -4266.763268131688,
			"y": -1211.0766657946228,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1a",
			"roundness": null,
			"seed": 1409297151,
			"version": 449,
			"versionNonce": 503656593,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "cTKq8f48uV4UkfpWyi2BR",
			"type": "freedraw",
			"x": -4020.304787472869,
			"y": -1209.1730652852134,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1b",
			"roundness": null,
			"seed": 1306555167,
			"version": 522,
			"versionNonce": 806549105,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "7TUl1w7ZzwbDgzoaBkTje",
			"type": "freedraw",
			"x": -3694.119597237098,
			"y": -1216.2275204958091,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1c",
			"roundness": null,
			"seed": 281196351,
			"version": 622,
			"versionNonce": 741146705,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "wArUwYKdWXhiO9UPBxW_i",
			"type": "freedraw",
			"x": -4266.763268131688,
			"y": -1192.2646941069793,
			"width": 0,
			"height": 2.6873757092766803,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1d",
			"roundness": null,
			"seed": 587691871,
			"version": 452,
			"versionNonce": 271240753,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.8957919030922542
				],
				[
					0,
					1.7915838061845084
				],
				[
					0,
					2.6873757092766803
				],
				[
					0,
					2.6873757092766803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "fbL31OB01cn_IjLYVtKok",
			"type": "freedraw",
			"x": -4020.304787472869,
			"y": -1190.3610935975698,
			"width": 0,
			"height": 2.6873757092766803,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1e",
			"roundness": null,
			"seed": 1795109759,
			"version": 525,
			"versionNonce": 854843409,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.8957919030922542
				],
				[
					0,
					1.7915838061845084
				],
				[
					0,
					2.6873757092766803
				],
				[
					0,
					2.6873757092766803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "jcNHVAjREOroWjdXw0nT5",
			"type": "freedraw",
			"x": -3694.119597237098,
			"y": -1197.4155488081656,
			"width": 0,
			"height": 2.6873757092766803,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1f",
			"roundness": null,
			"seed": 820669343,
			"version": 625,
			"versionNonce": 578794993,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.8957919030922542
				],
				[
					0,
					1.7915838061845084
				],
				[
					0,
					2.6873757092766803
				],
				[
					0,
					2.6873757092766803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "BiUE9FutcoCQTLXHFQYVd",
			"type": "freedraw",
			"x": -3704.3485382773206,
			"y": -489.5170829204819,
			"width": 0,
			"height": 2.6873757092766803,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1g",
			"roundness": null,
			"seed": 1626972095,
			"version": 703,
			"versionNonce": 1104531409,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.8957919030922542
				],
				[
					0,
					1.7915838061845084
				],
				[
					0,
					2.6873757092766803
				],
				[
					0,
					2.6873757092766803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "Yj5Xl4ez3cgVH0DBPFHLt",
			"type": "freedraw",
			"x": -4271.242295991691,
			"y": -1160.0157071838698,
			"width": 8.062263816912562,
			"height": 34.04063907383526,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1h",
			"roundness": null,
			"seed": 223170527,
			"version": 479,
			"versionNonce": 655207857,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8957919030920889,
					-1.7916521507257277
				],
				[
					1.7915838061843434,
					-1.7916521507257277
				],
				[
					2.6874440538179822,
					-4.479027860002492
				],
				[
					3.5832359569102366,
					-6.270680010728219
				],
				[
					5.374819763094581,
					-8.06226381691273
				],
				[
					6.270611666186833,
					-9.853847623097238
				],
				[
					6.270611666186833,
					-10.74970787073071
				],
				[
					7.166471913820473,
					-11.645499773822966
				],
				[
					7.166471913820473,
					-12.54129167691522
				],
				[
					8.062263816912562,
					-13.437083580007391
				],
				[
					8.062263816912562,
					-14.332875483099645
				],
				[
					8.062263816912562,
					-15.228735730733204
				],
				[
					8.062263816912562,
					-13.437083580007391
				],
				[
					8.062263816912562,
					-11.645499773822966
				],
				[
					8.062263816912562,
					-8.958055720004984
				],
				[
					7.166471913820473,
					-6.270680010728219
				],
				[
					7.166471913820473,
					-3.583235956910237
				],
				[
					7.166471913820473,
					0
				],
				[
					7.166471913820473,
					2.6873757092765977
				],
				[
					7.166471913820473,
					6.270611666186834
				],
				[
					6.270611666186833,
					9.853847623097073
				],
				[
					6.270611666186833,
					12.54129167691522
				],
				[
					6.270611666186833,
					15.228667386191816
				],
				[
					6.270611666186833,
					16.124459289284072
				],
				[
					6.270611666186833,
					17.020319536917548
				],
				[
					6.270611666186833,
					17.916111440009804
				],
				[
					6.270611666186833,
					18.811903343102056
				],
				[
					6.270611666186833,
					17.916111440009804
				],
				[
					6.270611666186833,
					17.020319536917548
				],
				[
					6.270611666186833,
					15.228667386191816
				],
				[
					6.270611666186833,
					15.228667386191816
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "qHM5b3e2cCqKCI44dQmA_",
			"type": "freedraw",
			"x": -4273.033879797875,
			"y": -1142.09959574386,
			"width": 17.020251192376325,
			"height": 4.479027860002492,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1i",
			"roundness": null,
			"seed": 804649983,
			"version": 467,
			"versionNonce": 961466257,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8957919030922543,
					-0.8957919030922545
				],
				[
					1.7915838061845086,
					-0.8957919030922545
				],
				[
					2.6873757092765973,
					-0.8957919030922545
				],
				[
					3.583167612368852,
					-0.8957919030922545
				],
				[
					4.479027860002491,
					-1.7916521507257281
				],
				[
					5.374819763094745,
					-1.7916521507257281
				],
				[
					6.270611666186833,
					-1.7916521507257281
				],
				[
					8.062195472371343,
					-2.687444053817983
				],
				[
					8.958055720004982,
					-2.687444053817983
				],
				[
					9.85384762309707,
					-2.687444053817983
				],
				[
					10.749639526189323,
					-3.583235956910237
				],
				[
					11.645431429281578,
					-3.583235956910237
				],
				[
					12.541223332373834,
					-3.583235956910237
				],
				[
					13.437083580007307,
					-3.583235956910237
				],
				[
					14.33287548309956,
					-4.479027860002492
				],
				[
					15.228667386191814,
					-4.479027860002492
				],
				[
					16.12445928928407,
					-4.479027860002492
				],
				[
					17.020251192376325,
					-4.479027860002492
				],
				[
					17.020251192376325,
					-4.479027860002492
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "pXJqszesPEwrGoWXa8OY2",
			"type": "freedraw",
			"x": -4247.055572885494,
			"y": -1339.1768215839684,
			"width": 29.561611213832762,
			"height": 200.66046179701877,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1j",
			"roundness": null,
			"seed": 754197535,
			"version": 617,
			"versionNonce": 248558961,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8958602476334733,
					0
				],
				[
					1.7916521507257275,
					0
				],
				[
					2.6874440538179822,
					0
				],
				[
					3.5832359569102366,
					0
				],
				[
					4.479027860002491,
					0
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					2.6874440538179822,
					-0.8957919030922544
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					5.3748881076359645,
					-0.8957919030922544
				],
				[
					6.270680010728219,
					-0.8957919030922544
				],
				[
					7.166471913820473,
					-0.8957919030922544
				],
				[
					8.062263816912727,
					-0.8957919030922544
				],
				[
					8.958055720004982,
					-0.8957919030922544
				],
				[
					9.853915967638455,
					-0.8957919030922544
				],
				[
					10.749707870730708,
					-0.8957919030922544
				],
				[
					11.645499773822964,
					-0.8957919030922544
				],
				[
					13.437083580007473,
					-0.8957919030922544
				],
				[
					15.228735730733202,
					-0.8957919030922544
				],
				[
					17.020319536917707,
					-0.8957919030922544
				],
				[
					18.81197168764344,
					-1.7916521507258105
				],
				[
					20.603555493827947,
					-1.7916521507258105
				],
				[
					22.39513930001229,
					-1.7916521507258105
				],
				[
					23.290999547645928,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					0
				],
				[
					24.18679145073818,
					1.791583806184426
				],
				[
					25.08258335383027,
					5.374819763094663
				],
				[
					25.08258335383027,
					8.06226381691273
				],
				[
					25.08258335383027,
					9.853847623097156
				],
				[
					25.978375256922526,
					12.541291676915137
				],
				[
					25.978375256922526,
					14.332875483099645
				],
				[
					26.87416716001478,
					16.12445928928407
				],
				[
					26.87416716001478,
					17.02031953691763
				],
				[
					26.87416716001478,
					18.811903343102138
				],
				[
					26.87416716001478,
					20.60348714928656
				],
				[
					26.87416716001478,
					21.499347396920122
				],
				[
					26.87416716001478,
					23.29093120310455
				],
				[
					26.87416716001478,
					24.1867231061968
				],
				[
					26.87416716001478,
					25.082515009289054
				],
				[
					26.87416716001478,
					26.874167160014782
				],
				[
					26.87416716001478,
					27.769959063107038
				],
				[
					26.87416716001478,
					29.561542869291458
				],
				[
					26.87416716001478,
					30.457403116925025
				],
				[
					26.87416716001478,
					32.248986923109534
				],
				[
					26.87416716001478,
					34.04057072929396
				],
				[
					26.87416716001478,
					35.83222288001977
				],
				[
					26.87416716001478,
					36.72801478311194
				],
				[
					26.87416716001478,
					37.62380668620419
				],
				[
					26.87416716001478,
					38.51959858929645
				],
				[
					26.87416716001478,
					40.31125074002218
				],
				[
					26.87416716001478,
					41.20704264311443
				],
				[
					26.87416716001478,
					42.10283454620669
				],
				[
					26.87416716001478,
					42.99862644929886
				],
				[
					26.87416716001478,
					44.79027860002466
				],
				[
					26.87416716001478,
					45.68607050311692
				],
				[
					26.87416716001478,
					47.47765430930134
				],
				[
					26.87416716001478,
					49.26930646002716
				],
				[
					26.87416716001478,
					51.95668216930384
				],
				[
					26.87416716001478,
					53.748334320029564
				],
				[
					26.87416716001478,
					55.539918126214076
				],
				[
					26.87416716001478,
					56.435710029306236
				],
				[
					26.87416716001478,
					58.22736218003205
				],
				[
					26.87416716001478,
					60.01894598621649
				],
				[
					26.87416716001478,
					61.8105981369423
				],
				[
					26.87416716001478,
					62.70639004003454
				],
				[
					26.87416716001478,
					65.39376574931123
				],
				[
					26.87416716001478,
					67.18541790003695
				],
				[
					26.87416716001478,
					68.97700170622147
				],
				[
					26.87416716001478,
					70.7686538569472
				],
				[
					26.87416716001478,
					73.45602956622395
				],
				[
					26.87416716001478,
					75.24768171694969
				],
				[
					26.87416716001478,
					77.03926552313412
				],
				[
					26.87416716001478,
					78.83084932931862
				],
				[
					26.87416716001478,
					80.62250148004436
				],
				[
					27.77002740764842,
					82.41408528622885
				],
				[
					27.77002740764842,
					83.30987718932111
				],
				[
					27.77002740764842,
					85.10152934004684
				],
				[
					27.77002740764842,
					86.89311314623136
				],
				[
					27.77002740764842,
					87.78890504932352
				],
				[
					27.77002740764842,
					89.58055720004933
				],
				[
					27.77002740764842,
					90.4763491031416
				],
				[
					27.77002740764842,
					91.37214100623376
				],
				[
					27.77002740764842,
					94.05958506005182
				],
				[
					27.77002740764842,
					95.85116886623625
				],
				[
					27.77002740764842,
					97.64282101696206
				],
				[
					27.77002740764842,
					98.53861292005422
				],
				[
					27.77002740764842,
					100.33019672623875
				],
				[
					27.77002740764842,
					102.12184887696446
				],
				[
					27.77002740764842,
					103.91343268314898
				],
				[
					27.77002740764842,
					104.80922458624116
				],
				[
					28.66581931074051,
					106.60087673696695
				],
				[
					28.66581931074051,
					107.49666864005923
				],
				[
					28.66581931074051,
					109.28825244624365
				],
				[
					28.66581931074051,
					110.18404434933589
				],
				[
					28.66581931074051,
					111.07990459696947
				],
				[
					28.66581931074051,
					113.76728030624612
				],
				[
					28.66581931074051,
					114.6630722093383
				],
				[
					29.561611213832762,
					115.55893245697187
				],
				[
					29.561611213832762,
					116.4547243600641
				],
				[
					29.561611213832762,
					117.35051626315638
				],
				[
					29.561611213832762,
					118.24630816624855
				],
				[
					29.561611213832762,
					120.03796031697436
				],
				[
					29.561611213832762,
					120.93375222006661
				],
				[
					29.561611213832762,
					122.72533602625103
				],
				[
					29.561611213832762,
					124.51698817697682
				],
				[
					29.561611213832762,
					125.41278008006901
				],
				[
					29.561611213832762,
					127.20436388625352
				],
				[
					29.561611213832762,
					128.10015578934568
				],
				[
					29.561611213832762,
					128.99601603697923
				],
				[
					29.561611213832762,
					130.78759984316378
				],
				[
					29.561611213832762,
					131.68339174625592
				],
				[
					29.561611213832762,
					133.47504389698173
				],
				[
					29.561611213832762,
					135.26662770316617
				],
				[
					29.561611213832762,
					137.05821150935068
				],
				[
					29.561611213832762,
					137.95407175698423
				],
				[
					29.561611213832762,
					138.84986366007638
				],
				[
					29.561611213832762,
					139.74565556316867
				],
				[
					29.561611213832762,
					141.53723936935316
				],
				[
					29.561611213832762,
					142.43309961698662
				],
				[
					29.561611213832762,
					143.3288915200789
				],
				[
					29.561611213832762,
					144.22468342317114
				],
				[
					29.561611213832762,
					146.01626722935558
				],
				[
					29.561611213832762,
					147.8079193800814
				],
				[
					29.561611213832762,
					148.70371128317365
				],
				[
					29.561611213832762,
					150.49529508935808
				],
				[
					29.561611213832762,
					151.39115533699163
				],
				[
					29.561611213832762,
					153.18273914317606
				],
				[
					29.561611213832762,
					154.0785310462683
				],
				[
					29.561611213832762,
					155.8701831969941
				],
				[
					29.561611213832762,
					157.6617670031785
				],
				[
					29.561611213832762,
					159.45335080936295
				],
				[
					29.561611213832762,
					160.34921105699652
				],
				[
					29.561611213832762,
					162.14079486318104
				],
				[
					29.561611213832762,
					163.93237866936548
				],
				[
					29.561611213832762,
					164.82823891699903
				],
				[
					29.561611213832762,
					166.61982272318343
				],
				[
					29.561611213832762,
					168.41140652936795
				],
				[
					29.561611213832762,
					170.20305868009368
				],
				[
					29.561611213832762,
					171.09885058318594
				],
				[
					29.561611213832762,
					172.89043438937043
				],
				[
					29.561611213832762,
					173.78629463700392
				],
				[
					29.561611213832762,
					174.68208654009618
				],
				[
					29.561611213832762,
					175.5778784431884
				],
				[
					29.561611213832762,
					176.47367034628067
				],
				[
					29.561611213832762,
					177.36946224937296
				],
				[
					29.561611213832762,
					178.26532249700642
				],
				[
					29.561611213832762,
					179.16111440009865
				],
				[
					29.561611213832762,
					180.05690630319094
				],
				[
					29.561611213832762,
					180.9526982062832
				],
				[
					29.561611213832762,
					181.84849010937526
				],
				[
					29.561611213832762,
					182.7443503570089
				],
				[
					29.561611213832762,
					183.6401422601012
				],
				[
					29.561611213832762,
					184.53593416319342
				],
				[
					29.561611213832762,
					185.4317260662855
				],
				[
					29.561611213832762,
					186.32751796937777
				],
				[
					29.561611213832762,
					187.2233782170114
				],
				[
					29.561611213832762,
					188.11917012010363
				],
				[
					29.561611213832762,
					189.01496202319575
				],
				[
					29.561611213832762,
					189.910753926288
				],
				[
					29.561611213832762,
					190.80654582938024
				],
				[
					29.561611213832762,
					192.598197980106
				],
				[
					29.561611213832762,
					193.49398988319822
				],
				[
					29.561611213832762,
					194.38978178629048
				],
				[
					29.561611213832762,
					195.28557368938274
				],
				[
					29.561611213832762,
					196.1814339370162
				],
				[
					29.561611213832762,
					197.07722584010844
				],
				[
					29.561611213832762,
					197.97301774320073
				],
				[
					29.561611213832762,
					198.86880964629296
				],
				[
					29.561611213832762,
					198.86880964629296
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "R4bUnwcSwVRYzX-n7AIcy",
			"type": "freedraw",
			"x": -3983.8247128847797,
			"y": -636.6933194524909,
			"width": 29.561611213832762,
			"height": 200.66046179701877,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1k",
			"roundness": null,
			"seed": 339232831,
			"version": 734,
			"versionNonce": 182116177,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8958602476334733,
					0
				],
				[
					1.7916521507257275,
					0
				],
				[
					2.6874440538179822,
					0
				],
				[
					3.5832359569102366,
					0
				],
				[
					4.479027860002491,
					0
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					2.6874440538179822,
					-0.8957919030922544
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					5.3748881076359645,
					-0.8957919030922544
				],
				[
					6.270680010728219,
					-0.8957919030922544
				],
				[
					7.166471913820473,
					-0.8957919030922544
				],
				[
					8.062263816912727,
					-0.8957919030922544
				],
				[
					8.958055720004982,
					-0.8957919030922544
				],
				[
					9.853915967638455,
					-0.8957919030922544
				],
				[
					10.749707870730708,
					-0.8957919030922544
				],
				[
					11.645499773822964,
					-0.8957919030922544
				],
				[
					13.437083580007473,
					-0.8957919030922544
				],
				[
					15.228735730733202,
					-0.8957919030922544
				],
				[
					17.020319536917707,
					-0.8957919030922544
				],
				[
					18.81197168764344,
					-1.7916521507258105
				],
				[
					20.603555493827947,
					-1.7916521507258105
				],
				[
					22.39513930001229,
					-1.7916521507258105
				],
				[
					23.290999547645928,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					0
				],
				[
					24.18679145073818,
					1.791583806184426
				],
				[
					25.08258335383027,
					5.374819763094663
				],
				[
					25.08258335383027,
					8.06226381691273
				],
				[
					25.08258335383027,
					9.853847623097156
				],
				[
					25.978375256922526,
					12.541291676915137
				],
				[
					25.978375256922526,
					14.332875483099645
				],
				[
					26.87416716001478,
					16.12445928928407
				],
				[
					26.87416716001478,
					17.02031953691763
				],
				[
					26.87416716001478,
					18.811903343102138
				],
				[
					26.87416716001478,
					20.60348714928656
				],
				[
					26.87416716001478,
					21.499347396920122
				],
				[
					26.87416716001478,
					23.29093120310455
				],
				[
					26.87416716001478,
					24.1867231061968
				],
				[
					26.87416716001478,
					25.082515009289054
				],
				[
					26.87416716001478,
					26.874167160014782
				],
				[
					26.87416716001478,
					27.769959063107038
				],
				[
					26.87416716001478,
					29.561542869291458
				],
				[
					26.87416716001478,
					30.457403116925025
				],
				[
					26.87416716001478,
					32.248986923109534
				],
				[
					26.87416716001478,
					34.04057072929396
				],
				[
					26.87416716001478,
					35.83222288001977
				],
				[
					26.87416716001478,
					36.72801478311194
				],
				[
					26.87416716001478,
					37.62380668620419
				],
				[
					26.87416716001478,
					38.51959858929645
				],
				[
					26.87416716001478,
					40.31125074002218
				],
				[
					26.87416716001478,
					41.20704264311443
				],
				[
					26.87416716001478,
					42.10283454620669
				],
				[
					26.87416716001478,
					42.99862644929886
				],
				[
					26.87416716001478,
					44.79027860002466
				],
				[
					26.87416716001478,
					45.68607050311692
				],
				[
					26.87416716001478,
					47.47765430930134
				],
				[
					26.87416716001478,
					49.26930646002716
				],
				[
					26.87416716001478,
					51.95668216930384
				],
				[
					26.87416716001478,
					53.748334320029564
				],
				[
					26.87416716001478,
					55.539918126214076
				],
				[
					26.87416716001478,
					56.435710029306236
				],
				[
					26.87416716001478,
					58.22736218003205
				],
				[
					26.87416716001478,
					60.01894598621649
				],
				[
					26.87416716001478,
					61.8105981369423
				],
				[
					26.87416716001478,
					62.70639004003454
				],
				[
					26.87416716001478,
					65.39376574931123
				],
				[
					26.87416716001478,
					67.18541790003695
				],
				[
					26.87416716001478,
					68.97700170622147
				],
				[
					26.87416716001478,
					70.7686538569472
				],
				[
					26.87416716001478,
					73.45602956622395
				],
				[
					26.87416716001478,
					75.24768171694969
				],
				[
					26.87416716001478,
					77.03926552313412
				],
				[
					26.87416716001478,
					78.83084932931862
				],
				[
					26.87416716001478,
					80.62250148004436
				],
				[
					27.77002740764842,
					82.41408528622885
				],
				[
					27.77002740764842,
					83.30987718932111
				],
				[
					27.77002740764842,
					85.10152934004684
				],
				[
					27.77002740764842,
					86.89311314623136
				],
				[
					27.77002740764842,
					87.78890504932352
				],
				[
					27.77002740764842,
					89.58055720004933
				],
				[
					27.77002740764842,
					90.4763491031416
				],
				[
					27.77002740764842,
					91.37214100623376
				],
				[
					27.77002740764842,
					94.05958506005182
				],
				[
					27.77002740764842,
					95.85116886623625
				],
				[
					27.77002740764842,
					97.64282101696206
				],
				[
					27.77002740764842,
					98.53861292005422
				],
				[
					27.77002740764842,
					100.33019672623875
				],
				[
					27.77002740764842,
					102.12184887696446
				],
				[
					27.77002740764842,
					103.91343268314898
				],
				[
					27.77002740764842,
					104.80922458624116
				],
				[
					28.66581931074051,
					106.60087673696695
				],
				[
					28.66581931074051,
					107.49666864005923
				],
				[
					28.66581931074051,
					109.28825244624365
				],
				[
					28.66581931074051,
					110.18404434933589
				],
				[
					28.66581931074051,
					111.07990459696947
				],
				[
					28.66581931074051,
					113.76728030624612
				],
				[
					28.66581931074051,
					114.6630722093383
				],
				[
					29.561611213832762,
					115.55893245697187
				],
				[
					29.561611213832762,
					116.4547243600641
				],
				[
					29.561611213832762,
					117.35051626315638
				],
				[
					29.561611213832762,
					118.24630816624855
				],
				[
					29.561611213832762,
					120.03796031697436
				],
				[
					29.561611213832762,
					120.93375222006661
				],
				[
					29.561611213832762,
					122.72533602625103
				],
				[
					29.561611213832762,
					124.51698817697682
				],
				[
					29.561611213832762,
					125.41278008006901
				],
				[
					29.561611213832762,
					127.20436388625352
				],
				[
					29.561611213832762,
					128.10015578934568
				],
				[
					29.561611213832762,
					128.99601603697923
				],
				[
					29.561611213832762,
					130.78759984316378
				],
				[
					29.561611213832762,
					131.68339174625592
				],
				[
					29.561611213832762,
					133.47504389698173
				],
				[
					29.561611213832762,
					135.26662770316617
				],
				[
					29.561611213832762,
					137.05821150935068
				],
				[
					29.561611213832762,
					137.95407175698423
				],
				[
					29.561611213832762,
					138.84986366007638
				],
				[
					29.561611213832762,
					139.74565556316867
				],
				[
					29.561611213832762,
					141.53723936935316
				],
				[
					29.561611213832762,
					142.43309961698662
				],
				[
					29.561611213832762,
					143.3288915200789
				],
				[
					29.561611213832762,
					144.22468342317114
				],
				[
					29.561611213832762,
					146.01626722935558
				],
				[
					29.561611213832762,
					147.8079193800814
				],
				[
					29.561611213832762,
					148.70371128317365
				],
				[
					29.561611213832762,
					150.49529508935808
				],
				[
					29.561611213832762,
					151.39115533699163
				],
				[
					29.561611213832762,
					153.18273914317606
				],
				[
					29.561611213832762,
					154.0785310462683
				],
				[
					29.561611213832762,
					155.8701831969941
				],
				[
					29.561611213832762,
					157.6617670031785
				],
				[
					29.561611213832762,
					159.45335080936295
				],
				[
					29.561611213832762,
					160.34921105699652
				],
				[
					29.561611213832762,
					162.14079486318104
				],
				[
					29.561611213832762,
					163.93237866936548
				],
				[
					29.561611213832762,
					164.82823891699903
				],
				[
					29.561611213832762,
					166.61982272318343
				],
				[
					29.561611213832762,
					168.41140652936795
				],
				[
					29.561611213832762,
					170.20305868009368
				],
				[
					29.561611213832762,
					171.09885058318594
				],
				[
					29.561611213832762,
					172.89043438937043
				],
				[
					29.561611213832762,
					173.78629463700392
				],
				[
					29.561611213832762,
					174.68208654009618
				],
				[
					29.561611213832762,
					175.5778784431884
				],
				[
					29.561611213832762,
					176.47367034628067
				],
				[
					29.561611213832762,
					177.36946224937296
				],
				[
					29.561611213832762,
					178.26532249700642
				],
				[
					29.561611213832762,
					179.16111440009865
				],
				[
					29.561611213832762,
					180.05690630319094
				],
				[
					29.561611213832762,
					180.9526982062832
				],
				[
					29.561611213832762,
					181.84849010937526
				],
				[
					29.561611213832762,
					182.7443503570089
				],
				[
					29.561611213832762,
					183.6401422601012
				],
				[
					29.561611213832762,
					184.53593416319342
				],
				[
					29.561611213832762,
					185.4317260662855
				],
				[
					29.561611213832762,
					186.32751796937777
				],
				[
					29.561611213832762,
					187.2233782170114
				],
				[
					29.561611213832762,
					188.11917012010363
				],
				[
					29.561611213832762,
					189.01496202319575
				],
				[
					29.561611213832762,
					189.910753926288
				],
				[
					29.561611213832762,
					190.80654582938024
				],
				[
					29.561611213832762,
					192.598197980106
				],
				[
					29.561611213832762,
					193.49398988319822
				],
				[
					29.561611213832762,
					194.38978178629048
				],
				[
					29.561611213832762,
					195.28557368938274
				],
				[
					29.561611213832762,
					196.1814339370162
				],
				[
					29.561611213832762,
					197.07722584010844
				],
				[
					29.561611213832762,
					197.97301774320073
				],
				[
					29.561611213832762,
					198.86880964629296
				],
				[
					29.561611213832762,
					198.86880964629296
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "-8GfikONmeC7LunTSZw4m",
			"type": "freedraw",
			"x": -4000.597092226675,
			"y": -1337.273221074559,
			"width": 29.561611213832762,
			"height": 200.66046179701877,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1l",
			"roundness": null,
			"seed": 597878879,
			"version": 692,
			"versionNonce": 1002753329,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8958602476334733,
					0
				],
				[
					1.7916521507257275,
					0
				],
				[
					2.6874440538179822,
					0
				],
				[
					3.5832359569102366,
					0
				],
				[
					4.479027860002491,
					0
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					2.6874440538179822,
					-0.8957919030922544
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					5.3748881076359645,
					-0.8957919030922544
				],
				[
					6.270680010728219,
					-0.8957919030922544
				],
				[
					7.166471913820473,
					-0.8957919030922544
				],
				[
					8.062263816912727,
					-0.8957919030922544
				],
				[
					8.958055720004982,
					-0.8957919030922544
				],
				[
					9.853915967638455,
					-0.8957919030922544
				],
				[
					10.749707870730708,
					-0.8957919030922544
				],
				[
					11.645499773822964,
					-0.8957919030922544
				],
				[
					13.437083580007473,
					-0.8957919030922544
				],
				[
					15.228735730733202,
					-0.8957919030922544
				],
				[
					17.020319536917707,
					-0.8957919030922544
				],
				[
					18.81197168764344,
					-1.7916521507258105
				],
				[
					20.603555493827947,
					-1.7916521507258105
				],
				[
					22.39513930001229,
					-1.7916521507258105
				],
				[
					23.290999547645928,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					0
				],
				[
					24.18679145073818,
					1.791583806184426
				],
				[
					25.08258335383027,
					5.374819763094663
				],
				[
					25.08258335383027,
					8.06226381691273
				],
				[
					25.08258335383027,
					9.853847623097156
				],
				[
					25.978375256922526,
					12.541291676915137
				],
				[
					25.978375256922526,
					14.332875483099645
				],
				[
					26.87416716001478,
					16.12445928928407
				],
				[
					26.87416716001478,
					17.02031953691763
				],
				[
					26.87416716001478,
					18.811903343102138
				],
				[
					26.87416716001478,
					20.60348714928656
				],
				[
					26.87416716001478,
					21.499347396920122
				],
				[
					26.87416716001478,
					23.29093120310455
				],
				[
					26.87416716001478,
					24.1867231061968
				],
				[
					26.87416716001478,
					25.082515009289054
				],
				[
					26.87416716001478,
					26.874167160014782
				],
				[
					26.87416716001478,
					27.769959063107038
				],
				[
					26.87416716001478,
					29.561542869291458
				],
				[
					26.87416716001478,
					30.457403116925025
				],
				[
					26.87416716001478,
					32.248986923109534
				],
				[
					26.87416716001478,
					34.04057072929396
				],
				[
					26.87416716001478,
					35.83222288001977
				],
				[
					26.87416716001478,
					36.72801478311194
				],
				[
					26.87416716001478,
					37.62380668620419
				],
				[
					26.87416716001478,
					38.51959858929645
				],
				[
					26.87416716001478,
					40.31125074002218
				],
				[
					26.87416716001478,
					41.20704264311443
				],
				[
					26.87416716001478,
					42.10283454620669
				],
				[
					26.87416716001478,
					42.99862644929886
				],
				[
					26.87416716001478,
					44.79027860002466
				],
				[
					26.87416716001478,
					45.68607050311692
				],
				[
					26.87416716001478,
					47.47765430930134
				],
				[
					26.87416716001478,
					49.26930646002716
				],
				[
					26.87416716001478,
					51.95668216930384
				],
				[
					26.87416716001478,
					53.748334320029564
				],
				[
					26.87416716001478,
					55.539918126214076
				],
				[
					26.87416716001478,
					56.435710029306236
				],
				[
					26.87416716001478,
					58.22736218003205
				],
				[
					26.87416716001478,
					60.01894598621649
				],
				[
					26.87416716001478,
					61.8105981369423
				],
				[
					26.87416716001478,
					62.70639004003454
				],
				[
					26.87416716001478,
					65.39376574931123
				],
				[
					26.87416716001478,
					67.18541790003695
				],
				[
					26.87416716001478,
					68.97700170622147
				],
				[
					26.87416716001478,
					70.7686538569472
				],
				[
					26.87416716001478,
					73.45602956622395
				],
				[
					26.87416716001478,
					75.24768171694969
				],
				[
					26.87416716001478,
					77.03926552313412
				],
				[
					26.87416716001478,
					78.83084932931862
				],
				[
					26.87416716001478,
					80.62250148004436
				],
				[
					27.77002740764842,
					82.41408528622885
				],
				[
					27.77002740764842,
					83.30987718932111
				],
				[
					27.77002740764842,
					85.10152934004684
				],
				[
					27.77002740764842,
					86.89311314623136
				],
				[
					27.77002740764842,
					87.78890504932352
				],
				[
					27.77002740764842,
					89.58055720004933
				],
				[
					27.77002740764842,
					90.4763491031416
				],
				[
					27.77002740764842,
					91.37214100623376
				],
				[
					27.77002740764842,
					94.05958506005182
				],
				[
					27.77002740764842,
					95.85116886623625
				],
				[
					27.77002740764842,
					97.64282101696206
				],
				[
					27.77002740764842,
					98.53861292005422
				],
				[
					27.77002740764842,
					100.33019672623875
				],
				[
					27.77002740764842,
					102.12184887696446
				],
				[
					27.77002740764842,
					103.91343268314898
				],
				[
					27.77002740764842,
					104.80922458624116
				],
				[
					28.66581931074051,
					106.60087673696695
				],
				[
					28.66581931074051,
					107.49666864005923
				],
				[
					28.66581931074051,
					109.28825244624365
				],
				[
					28.66581931074051,
					110.18404434933589
				],
				[
					28.66581931074051,
					111.07990459696947
				],
				[
					28.66581931074051,
					113.76728030624612
				],
				[
					28.66581931074051,
					114.6630722093383
				],
				[
					29.561611213832762,
					115.55893245697187
				],
				[
					29.561611213832762,
					116.4547243600641
				],
				[
					29.561611213832762,
					117.35051626315638
				],
				[
					29.561611213832762,
					118.24630816624855
				],
				[
					29.561611213832762,
					120.03796031697436
				],
				[
					29.561611213832762,
					120.93375222006661
				],
				[
					29.561611213832762,
					122.72533602625103
				],
				[
					29.561611213832762,
					124.51698817697682
				],
				[
					29.561611213832762,
					125.41278008006901
				],
				[
					29.561611213832762,
					127.20436388625352
				],
				[
					29.561611213832762,
					128.10015578934568
				],
				[
					29.561611213832762,
					128.99601603697923
				],
				[
					29.561611213832762,
					130.78759984316378
				],
				[
					29.561611213832762,
					131.68339174625592
				],
				[
					29.561611213832762,
					133.47504389698173
				],
				[
					29.561611213832762,
					135.26662770316617
				],
				[
					29.561611213832762,
					137.05821150935068
				],
				[
					29.561611213832762,
					137.95407175698423
				],
				[
					29.561611213832762,
					138.84986366007638
				],
				[
					29.561611213832762,
					139.74565556316867
				],
				[
					29.561611213832762,
					141.53723936935316
				],
				[
					29.561611213832762,
					142.43309961698662
				],
				[
					29.561611213832762,
					143.3288915200789
				],
				[
					29.561611213832762,
					144.22468342317114
				],
				[
					29.561611213832762,
					146.01626722935558
				],
				[
					29.561611213832762,
					147.8079193800814
				],
				[
					29.561611213832762,
					148.70371128317365
				],
				[
					29.561611213832762,
					150.49529508935808
				],
				[
					29.561611213832762,
					151.39115533699163
				],
				[
					29.561611213832762,
					153.18273914317606
				],
				[
					29.561611213832762,
					154.0785310462683
				],
				[
					29.561611213832762,
					155.8701831969941
				],
				[
					29.561611213832762,
					157.6617670031785
				],
				[
					29.561611213832762,
					159.45335080936295
				],
				[
					29.561611213832762,
					160.34921105699652
				],
				[
					29.561611213832762,
					162.14079486318104
				],
				[
					29.561611213832762,
					163.93237866936548
				],
				[
					29.561611213832762,
					164.82823891699903
				],
				[
					29.561611213832762,
					166.61982272318343
				],
				[
					29.561611213832762,
					168.41140652936795
				],
				[
					29.561611213832762,
					170.20305868009368
				],
				[
					29.561611213832762,
					171.09885058318594
				],
				[
					29.561611213832762,
					172.89043438937043
				],
				[
					29.561611213832762,
					173.78629463700392
				],
				[
					29.561611213832762,
					174.68208654009618
				],
				[
					29.561611213832762,
					175.5778784431884
				],
				[
					29.561611213832762,
					176.47367034628067
				],
				[
					29.561611213832762,
					177.36946224937296
				],
				[
					29.561611213832762,
					178.26532249700642
				],
				[
					29.561611213832762,
					179.16111440009865
				],
				[
					29.561611213832762,
					180.05690630319094
				],
				[
					29.561611213832762,
					180.9526982062832
				],
				[
					29.561611213832762,
					181.84849010937526
				],
				[
					29.561611213832762,
					182.7443503570089
				],
				[
					29.561611213832762,
					183.6401422601012
				],
				[
					29.561611213832762,
					184.53593416319342
				],
				[
					29.561611213832762,
					185.4317260662855
				],
				[
					29.561611213832762,
					186.32751796937777
				],
				[
					29.561611213832762,
					187.2233782170114
				],
				[
					29.561611213832762,
					188.11917012010363
				],
				[
					29.561611213832762,
					189.01496202319575
				],
				[
					29.561611213832762,
					189.910753926288
				],
				[
					29.561611213832762,
					190.80654582938024
				],
				[
					29.561611213832762,
					192.598197980106
				],
				[
					29.561611213832762,
					193.49398988319822
				],
				[
					29.561611213832762,
					194.38978178629048
				],
				[
					29.561611213832762,
					195.28557368938274
				],
				[
					29.561611213832762,
					196.1814339370162
				],
				[
					29.561611213832762,
					197.07722584010844
				],
				[
					29.561611213832762,
					197.97301774320073
				],
				[
					29.561611213832762,
					198.86880964629296
				],
				[
					29.561611213832762,
					198.86880964629296
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "VMy9eIAfWI950BYZbRU4U",
			"type": "freedraw",
			"x": -3674.411901990903,
			"y": -1344.3276762851547,
			"width": 29.561611213832762,
			"height": 200.66046179701877,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1m",
			"roundness": null,
			"seed": 151291007,
			"version": 792,
			"versionNonce": 2029387537,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8958602476334733,
					0
				],
				[
					1.7916521507257275,
					0
				],
				[
					2.6874440538179822,
					0
				],
				[
					3.5832359569102366,
					0
				],
				[
					4.479027860002491,
					0
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					2.6874440538179822,
					-0.8957919030922544
				],
				[
					3.5832359569102366,
					-0.8957919030922544
				],
				[
					5.3748881076359645,
					-0.8957919030922544
				],
				[
					6.270680010728219,
					-0.8957919030922544
				],
				[
					7.166471913820473,
					-0.8957919030922544
				],
				[
					8.062263816912727,
					-0.8957919030922544
				],
				[
					8.958055720004982,
					-0.8957919030922544
				],
				[
					9.853915967638455,
					-0.8957919030922544
				],
				[
					10.749707870730708,
					-0.8957919030922544
				],
				[
					11.645499773822964,
					-0.8957919030922544
				],
				[
					13.437083580007473,
					-0.8957919030922544
				],
				[
					15.228735730733202,
					-0.8957919030922544
				],
				[
					17.020319536917707,
					-0.8957919030922544
				],
				[
					18.81197168764344,
					-1.7916521507258105
				],
				[
					20.603555493827947,
					-1.7916521507258105
				],
				[
					22.39513930001229,
					-1.7916521507258105
				],
				[
					23.290999547645928,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					-1.7916521507258105
				],
				[
					24.18679145073818,
					0
				],
				[
					24.18679145073818,
					1.791583806184426
				],
				[
					25.08258335383027,
					5.374819763094663
				],
				[
					25.08258335383027,
					8.06226381691273
				],
				[
					25.08258335383027,
					9.853847623097156
				],
				[
					25.978375256922526,
					12.541291676915137
				],
				[
					25.978375256922526,
					14.332875483099645
				],
				[
					26.87416716001478,
					16.12445928928407
				],
				[
					26.87416716001478,
					17.02031953691763
				],
				[
					26.87416716001478,
					18.811903343102138
				],
				[
					26.87416716001478,
					20.60348714928656
				],
				[
					26.87416716001478,
					21.499347396920122
				],
				[
					26.87416716001478,
					23.29093120310455
				],
				[
					26.87416716001478,
					24.1867231061968
				],
				[
					26.87416716001478,
					25.082515009289054
				],
				[
					26.87416716001478,
					26.874167160014782
				],
				[
					26.87416716001478,
					27.769959063107038
				],
				[
					26.87416716001478,
					29.561542869291458
				],
				[
					26.87416716001478,
					30.457403116925025
				],
				[
					26.87416716001478,
					32.248986923109534
				],
				[
					26.87416716001478,
					34.04057072929396
				],
				[
					26.87416716001478,
					35.83222288001977
				],
				[
					26.87416716001478,
					36.72801478311194
				],
				[
					26.87416716001478,
					37.62380668620419
				],
				[
					26.87416716001478,
					38.51959858929645
				],
				[
					26.87416716001478,
					40.31125074002218
				],
				[
					26.87416716001478,
					41.20704264311443
				],
				[
					26.87416716001478,
					42.10283454620669
				],
				[
					26.87416716001478,
					42.99862644929886
				],
				[
					26.87416716001478,
					44.79027860002466
				],
				[
					26.87416716001478,
					45.68607050311692
				],
				[
					26.87416716001478,
					47.47765430930134
				],
				[
					26.87416716001478,
					49.26930646002716
				],
				[
					26.87416716001478,
					51.95668216930384
				],
				[
					26.87416716001478,
					53.748334320029564
				],
				[
					26.87416716001478,
					55.539918126214076
				],
				[
					26.87416716001478,
					56.435710029306236
				],
				[
					26.87416716001478,
					58.22736218003205
				],
				[
					26.87416716001478,
					60.01894598621649
				],
				[
					26.87416716001478,
					61.8105981369423
				],
				[
					26.87416716001478,
					62.70639004003454
				],
				[
					26.87416716001478,
					65.39376574931123
				],
				[
					26.87416716001478,
					67.18541790003695
				],
				[
					26.87416716001478,
					68.97700170622147
				],
				[
					26.87416716001478,
					70.7686538569472
				],
				[
					26.87416716001478,
					73.45602956622395
				],
				[
					26.87416716001478,
					75.24768171694969
				],
				[
					26.87416716001478,
					77.03926552313412
				],
				[
					26.87416716001478,
					78.83084932931862
				],
				[
					26.87416716001478,
					80.62250148004436
				],
				[
					27.77002740764842,
					82.41408528622885
				],
				[
					27.77002740764842,
					83.30987718932111
				],
				[
					27.77002740764842,
					85.10152934004684
				],
				[
					27.77002740764842,
					86.89311314623136
				],
				[
					27.77002740764842,
					87.78890504932352
				],
				[
					27.77002740764842,
					89.58055720004933
				],
				[
					27.77002740764842,
					90.4763491031416
				],
				[
					27.77002740764842,
					91.37214100623376
				],
				[
					27.77002740764842,
					94.05958506005182
				],
				[
					27.77002740764842,
					95.85116886623625
				],
				[
					27.77002740764842,
					97.64282101696206
				],
				[
					27.77002740764842,
					98.53861292005422
				],
				[
					27.77002740764842,
					100.33019672623875
				],
				[
					27.77002740764842,
					102.12184887696446
				],
				[
					27.77002740764842,
					103.91343268314898
				],
				[
					27.77002740764842,
					104.80922458624116
				],
				[
					28.66581931074051,
					106.60087673696695
				],
				[
					28.66581931074051,
					107.49666864005923
				],
				[
					28.66581931074051,
					109.28825244624365
				],
				[
					28.66581931074051,
					110.18404434933589
				],
				[
					28.66581931074051,
					111.07990459696947
				],
				[
					28.66581931074051,
					113.76728030624612
				],
				[
					28.66581931074051,
					114.6630722093383
				],
				[
					29.561611213832762,
					115.55893245697187
				],
				[
					29.561611213832762,
					116.4547243600641
				],
				[
					29.561611213832762,
					117.35051626315638
				],
				[
					29.561611213832762,
					118.24630816624855
				],
				[
					29.561611213832762,
					120.03796031697436
				],
				[
					29.561611213832762,
					120.93375222006661
				],
				[
					29.561611213832762,
					122.72533602625103
				],
				[
					29.561611213832762,
					124.51698817697682
				],
				[
					29.561611213832762,
					125.41278008006901
				],
				[
					29.561611213832762,
					127.20436388625352
				],
				[
					29.561611213832762,
					128.10015578934568
				],
				[
					29.561611213832762,
					128.99601603697923
				],
				[
					29.561611213832762,
					130.78759984316378
				],
				[
					29.561611213832762,
					131.68339174625592
				],
				[
					29.561611213832762,
					133.47504389698173
				],
				[
					29.561611213832762,
					135.26662770316617
				],
				[
					29.561611213832762,
					137.05821150935068
				],
				[
					29.561611213832762,
					137.95407175698423
				],
				[
					29.561611213832762,
					138.84986366007638
				],
				[
					29.561611213832762,
					139.74565556316867
				],
				[
					29.561611213832762,
					141.53723936935316
				],
				[
					29.561611213832762,
					142.43309961698662
				],
				[
					29.561611213832762,
					143.3288915200789
				],
				[
					29.561611213832762,
					144.22468342317114
				],
				[
					29.561611213832762,
					146.01626722935558
				],
				[
					29.561611213832762,
					147.8079193800814
				],
				[
					29.561611213832762,
					148.70371128317365
				],
				[
					29.561611213832762,
					150.49529508935808
				],
				[
					29.561611213832762,
					151.39115533699163
				],
				[
					29.561611213832762,
					153.18273914317606
				],
				[
					29.561611213832762,
					154.0785310462683
				],
				[
					29.561611213832762,
					155.8701831969941
				],
				[
					29.561611213832762,
					157.6617670031785
				],
				[
					29.561611213832762,
					159.45335080936295
				],
				[
					29.561611213832762,
					160.34921105699652
				],
				[
					29.561611213832762,
					162.14079486318104
				],
				[
					29.561611213832762,
					163.93237866936548
				],
				[
					29.561611213832762,
					164.82823891699903
				],
				[
					29.561611213832762,
					166.61982272318343
				],
				[
					29.561611213832762,
					168.41140652936795
				],
				[
					29.561611213832762,
					170.20305868009368
				],
				[
					29.561611213832762,
					171.09885058318594
				],
				[
					29.561611213832762,
					172.89043438937043
				],
				[
					29.561611213832762,
					173.78629463700392
				],
				[
					29.561611213832762,
					174.68208654009618
				],
				[
					29.561611213832762,
					175.5778784431884
				],
				[
					29.561611213832762,
					176.47367034628067
				],
				[
					29.561611213832762,
					177.36946224937296
				],
				[
					29.561611213832762,
					178.26532249700642
				],
				[
					29.561611213832762,
					179.16111440009865
				],
				[
					29.561611213832762,
					180.05690630319094
				],
				[
					29.561611213832762,
					180.9526982062832
				],
				[
					29.561611213832762,
					181.84849010937526
				],
				[
					29.561611213832762,
					182.7443503570089
				],
				[
					29.561611213832762,
					183.6401422601012
				],
				[
					29.561611213832762,
					184.53593416319342
				],
				[
					29.561611213832762,
					185.4317260662855
				],
				[
					29.561611213832762,
					186.32751796937777
				],
				[
					29.561611213832762,
					187.2233782170114
				],
				[
					29.561611213832762,
					188.11917012010363
				],
				[
					29.561611213832762,
					189.01496202319575
				],
				[
					29.561611213832762,
					189.910753926288
				],
				[
					29.561611213832762,
					190.80654582938024
				],
				[
					29.561611213832762,
					192.598197980106
				],
				[
					29.561611213832762,
					193.49398988319822
				],
				[
					29.561611213832762,
					194.38978178629048
				],
				[
					29.561611213832762,
					195.28557368938274
				],
				[
					29.561611213832762,
					196.1814339370162
				],
				[
					29.561611213832762,
					197.07722584010844
				],
				[
					29.561611213832762,
					197.97301774320073
				],
				[
					29.561611213832762,
					198.86880964629296
				],
				[
					29.561611213832762,
					198.86880964629296
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "S1_vY_nIqiJkQ378tYB3v",
			"type": "freedraw",
			"x": -4238.993309068581,
			"y": -1139.4122200345832,
			"width": 21.49934739692004,
			"height": 0,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1n",
			"roundness": null,
			"seed": 1679662239,
			"version": 472,
			"versionNonce": 1088812273,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8957919030922545,
					0
				],
				[
					1.791652150725728,
					0
				],
				[
					2.687444053817983,
					0
				],
				[
					3.5832359569102374,
					0
				],
				[
					4.479027860002493,
					0
				],
				[
					5.374819763094746,
					0
				],
				[
					6.270680010728221,
					0
				],
				[
					7.166471913820475,
					0
				],
				[
					8.958055720004985,
					0
				],
				[
					9.853847623097073,
					0
				],
				[
					10.749707870730711,
					0
				],
				[
					11.645499773822966,
					0
				],
				[
					12.541291676915222,
					0
				],
				[
					13.43708358000731,
					0
				],
				[
					14.332875483099563,
					0
				],
				[
					15.228735730733204,
					0
				],
				[
					16.12452763382546,
					0
				],
				[
					17.020319536917548,
					0
				],
				[
					17.916111440009804,
					0
				],
				[
					18.81190334310206,
					0
				],
				[
					19.7077635907357,
					0
				],
				[
					20.603555493827788,
					0
				],
				[
					21.49934739692004,
					0
				],
				[
					21.49934739692004,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "gRFQGRhs4fvEPlDUDyNWF",
			"type": "freedraw",
			"x": -3975.7624490678663,
			"y": -436.92871790310573,
			"width": 21.49934739692004,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1o",
			"roundness": null,
			"seed": 144617663,
			"version": 585,
			"versionNonce": 1461464785,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508772,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8957919030922545,
					0
				],
				[
					1.791652150725728,
					0
				],
				[
					2.687444053817983,
					0
				],
				[
					3.5832359569102374,
					0
				],
				[
					4.479027860002493,
					0
				],
				[
					5.374819763094746,
					0
				],
				[
					6.270680010728221,
					0
				],
				[
					7.166471913820475,
					0
				],
				[
					8.958055720004985,
					0
				],
				[
					9.853847623097073,
					0
				],
				[
					10.749707870730711,
					0
				],
				[
					11.645499773822966,
					0
				],
				[
					12.541291676915222,
					0
				],
				[
					13.43708358000731,
					0
				],
				[
					14.332875483099563,
					0
				],
				[
					15.228735730733204,
					0
				],
				[
					16.12452763382546,
					0
				],
				[
					17.020319536917548,
					0
				],
				[
					17.916111440009804,
					0
				],
				[
					18.81190334310206,
					0
				],
				[
					19.7077635907357,
					0
				],
				[
					20.603555493827788,
					0
				],
				[
					21.49934739692004,
					0
				],
				[
					21.49934739692004,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "ErDuFQV4iJlWJCvqGkjKI",
			"type": "freedraw",
			"x": -3992.5348284097618,
			"y": -1137.5086195251738,
			"width": 21.49934739692004,
			"height": 0,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1p",
			"roundness": null,
			"seed": 2638047,
			"version": 545,
			"versionNonce": 573582513,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8957919030922545,
					0
				],
				[
					1.791652150725728,
					0
				],
				[
					2.687444053817983,
					0
				],
				[
					3.5832359569102374,
					0
				],
				[
					4.479027860002493,
					0
				],
				[
					5.374819763094746,
					0
				],
				[
					6.270680010728221,
					0
				],
				[
					7.166471913820475,
					0
				],
				[
					8.958055720004985,
					0
				],
				[
					9.853847623097073,
					0
				],
				[
					10.749707870730711,
					0
				],
				[
					11.645499773822966,
					0
				],
				[
					12.541291676915222,
					0
				],
				[
					13.43708358000731,
					0
				],
				[
					14.332875483099563,
					0
				],
				[
					15.228735730733204,
					0
				],
				[
					16.12452763382546,
					0
				],
				[
					17.020319536917548,
					0
				],
				[
					17.916111440009804,
					0
				],
				[
					18.81190334310206,
					0
				],
				[
					19.7077635907357,
					0
				],
				[
					20.603555493827788,
					0
				],
				[
					21.49934739692004,
					0
				],
				[
					21.49934739692004,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "pTsuqVV-J8IxTXfNHGIQG",
			"type": "freedraw",
			"x": -3666.3496381739906,
			"y": -1144.5630747357695,
			"width": 21.49934739692004,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1q",
			"roundness": null,
			"seed": 1279970559,
			"version": 645,
			"versionNonce": 1237937809,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8957919030922545,
					0
				],
				[
					1.791652150725728,
					0
				],
				[
					2.687444053817983,
					0
				],
				[
					3.5832359569102374,
					0
				],
				[
					4.479027860002493,
					0
				],
				[
					5.374819763094746,
					0
				],
				[
					6.270680010728221,
					0
				],
				[
					7.166471913820475,
					0
				],
				[
					8.958055720004985,
					0
				],
				[
					9.853847623097073,
					0
				],
				[
					10.749707870730711,
					0
				],
				[
					11.645499773822966,
					0
				],
				[
					12.541291676915222,
					0
				],
				[
					13.43708358000731,
					0
				],
				[
					14.332875483099563,
					0
				],
				[
					15.228735730733204,
					0
				],
				[
					16.12452763382546,
					0
				],
				[
					17.020319536917548,
					0
				],
				[
					17.916111440009804,
					0
				],
				[
					18.81190334310206,
					0
				],
				[
					19.7077635907357,
					0
				],
				[
					20.603555493827788,
					0
				],
				[
					21.49934739692004,
					0
				],
				[
					21.49934739692004,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "7YVjn36wm6HgaNFHKt_Mh",
			"type": "freedraw",
			"x": -3916.5033031484036,
			"y": -1228.096916986999,
			"width": 1.7915838061845089,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1r",
			"roundness": null,
			"seed": 1753666847,
			"version": 486,
			"versionNonce": 345994353,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8957235585510355,
					0
				],
				[
					-1.7915838061845089,
					0
				],
				[
					-1.7915838061845089,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "OqPAhZidyT1oAcONLWF5d",
			"type": "freedraw",
			"x": -3837.6723854745433,
			"y": -1225.4095412777224,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1s",
			"roundness": null,
			"seed": 206362943,
			"version": 454,
			"versionNonce": 108641873,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "VYK-aRPHHtmYQnWEUGu2p",
			"type": "freedraw",
			"x": -3885.150108128386,
			"y": -1224.5137493746302,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1t",
			"roundness": null,
			"seed": 754800991,
			"version": 453,
			"versionNonce": 1043319857,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "PyclmawHubpdh9Le1l5lT",
			"type": "freedraw",
			"x": -3857.380080720738,
			"y": -1228.096916986999,
			"width": 0.00007278420272504008,
			"height": 0.00007278420272504008,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1u",
			"roundness": null,
			"seed": 1072223615,
			"version": 454,
			"versionNonce": 329850385,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007278420272504008,
					0.00007278420272504008
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "a461Ol2PNAXQvWsIiquk8",
			"type": "arrow",
			"x": -4265.465210372053,
			"y": -1400.4610417120398,
			"width": 184.08333259911217,
			"height": 137.55678364005723,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1v",
			"roundness": {
				"type": 2
			},
			"seed": 1011862943,
			"version": 428,
			"versionNonce": 1977431025,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					184.08333259911217,
					-137.55678364005723
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "v3etlgsPNtEfAJrdy4iam",
			"type": "arrow",
			"x": -4032.017064165725,
			"y": -689.855093946253,
			"width": 1.957182884250642,
			"height": 129.434234721935,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1w",
			"roundness": {
				"type": 2
			},
			"seed": 1566753215,
			"version": 665,
			"versionNonce": 148082129,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.957182884250642,
					-129.434234721935
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "GpADNe3yvGi74FDeC3cfv",
			"type": "arrow",
			"x": -4049.0154486409265,
			"y": -1372.1404933888139,
			"width": 32.366429132014105,
			"height": 149.69419456456262,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1x",
			"roundness": {
				"type": 2
			},
			"seed": 608317919,
			"version": 409,
			"versionNonce": 61057969,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-32.366429132014105,
					-149.69419456456262
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "fh6REGUAH_uddogw_Y0J8",
			"type": "arrow",
			"x": -3709.1693317659283,
			"y": -1366.0718265102041,
			"width": 345.91486092089406,
			"height": 173.96886207900104,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1y",
			"roundness": {
				"type": 2
			},
			"seed": 436116991,
			"version": 452,
			"versionNonce": 1316294033,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-345.91486092089406,
					-173.96886207900104
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "0xMiObAk",
			"type": "text",
			"x": -4504.166930715082,
			"y": -1590.6130411897616,
			"width": 1018.477783203125,
			"height": 37.87212640776936,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b1z",
			"roundness": null,
			"seed": 1368950303,
			"version": 684,
			"versionNonce": 1618948977,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "One-hot pseudo-labeling vector (i.e., ground truth) for training pixels",
			"rawText": "One-hot pseudo-labeling vector (i.e., ground truth) for training pixels",
			"fontSize": 30.297701126215486,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "One-hot pseudo-labeling vector (i.e., ground truth) for training pixels",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "tfqswOUx",
			"type": "text",
			"x": -4435.406863259193,
			"y": -896.2521912602197,
			"width": 911.3776245117188,
			"height": 32.733538772693834,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b20",
			"roundness": null,
			"seed": 704670271,
			"version": 1406,
			"versionNonce": 1577688401,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "an example output vector for each node after Graph Laplacian Learning",
			"rawText": "an example output vector for each node after Graph Laplacian Learning",
			"fontSize": 26.18683101815507,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "an example output vector for each node after Graph Laplacian Learning",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "7iZViievuGp8UB75TcTG_",
			"type": "rectangle",
			"x": -4520.34991377923,
			"y": -1663.437236651292,
			"width": 1049.8819936871876,
			"height": 590.6851323916037,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b21",
			"roundness": {
				"type": 3
			},
			"seed": 1343670879,
			"version": 437,
			"versionNonce": 1986775857,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "BEtc08yqsb8eEULDTgiCk",
			"type": "rectangle",
			"x": -4530.578854819452,
			"y": -952.8310823178792,
			"width": 1049.8819936871876,
			"height": 590.6851323916037,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b22",
			"roundness": {
				"type": 3
			},
			"seed": 11282047,
			"version": 516,
			"versionNonce": 34422033,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "GQVwnHSgrgnkay3YHbwip",
			"type": "arrow",
			"x": -2855.5080816023583,
			"y": -1341.7972361630514,
			"width": 436.9452499364684,
			"height": 362.09803690325805,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b23",
			"roundness": {
				"type": 2
			},
			"seed": 176225951,
			"version": 141,
			"versionNonce": 1617261297,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					436.9452499364684,
					-362.09803690325805
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "iDYRtLWN",
			"type": "text",
			"x": -1999.8241225362517,
			"y": -1784.8110372272004,
			"width": 645.643798828125,
			"height": 132.65241251407735,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b24",
			"roundness": null,
			"seed": 273011391,
			"version": 379,
			"versionNonce": 368831697,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "Terminate the loop until a number of \nM desired training pixels is reached\n(Assume that M = 3 in our example)",
			"rawText": "Terminate the loop until a number of \nM desired training pixels is reached\n(Assume that M = 3 in our example)",
			"fontSize": 35.37397667042063,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Terminate the loop until a number of \nM desired training pixels is reached\n(Assume that M = 3 in our example)",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "GH3h4kPrtRc8ZC5YYyypq",
			"type": "line",
			"x": -2895.9659636828037,
			"y": -467.90689062468687,
			"width": 414.69329132456585,
			"height": 258.9305070486794,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b25",
			"roundness": {
				"type": 2
			},
			"seed": 177939167,
			"version": 127,
			"versionNonce": 711469745,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-226.56423225123774,
					-99.12184196400563
				],
				[
					-414.69329132456585,
					-258.9305070486794
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "A9vYv8vRtaWnMVpp-Kr8d",
			"type": "ellipse",
			"x": -1806.4850534968473,
			"y": -1226.8167170978395,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b26",
			"roundness": {
				"type": 2
			},
			"seed": 168914687,
			"version": 190,
			"versionNonce": 1179757713,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "-Yfr-ivvfC2L-XGJ5sx8B",
			"type": "ellipse",
			"x": -2026.1666073876786,
			"y": -1165.6082374675198,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b27",
			"roundness": {
				"type": 2
			},
			"seed": 959002399,
			"version": 175,
			"versionNonce": 292549233,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "LDPl2_C9XvFjIyjvuZG_e",
			"type": "ellipse",
			"x": -2035.285010772238,
			"y": -1316.8167018390504,
			"width": 38.4000244140625,
			"height": 49,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b28",
			"roundness": {
				"type": 2
			},
			"seed": 508754751,
			"version": 274,
			"versionNonce": 1351253073,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "MmPhyP-VBiwLIIldIFDXU",
			"type": "ellipse",
			"x": -1951.285041289816,
			"y": -1365.2167109943239,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b29",
			"roundness": {
				"type": 2
			},
			"seed": 502217567,
			"version": 192,
			"versionNonce": 1131989553,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "kJT0nPhofbqg1-OmXp-xj",
			"type": "ellipse",
			"x": -2065.6850351863004,
			"y": -1228.4167232013551,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2A",
			"roundness": {
				"type": 2
			},
			"seed": 1011775359,
			"version": 192,
			"versionNonce": 1126325265,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "oRJ1Pi6fcl5vwosRSS2KH",
			"type": "ellipse",
			"x": -1937.6850657038785,
			"y": -1192.4167232013551,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2B",
			"roundness": {
				"type": 2
			},
			"seed": 531705759,
			"version": 192,
			"versionNonce": 528396785,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "gtQyCiNZcIWVWbQuzjNuG",
			"type": "ellipse",
			"x": -1852.8850168757535,
			"y": -1337.2167109943239,
			"width": 38.4000244140625,
			"height": 34.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2C",
			"roundness": {
				"type": 2
			},
			"seed": 1380443071,
			"version": 192,
			"versionNonce": 1033194449,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "SH-52Q79g3m3JFgSN7oN1",
			"type": "line",
			"x": -2004.8850168757535,
			"y": -1316.0167140460817,
			"width": 55.20001220703125,
			"height": 20.800018310546875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2D",
			"roundness": {
				"type": 2
			},
			"seed": 1144198111,
			"version": 104,
			"versionNonce": 1971169713,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.20001220703125,
					-20.800018310546875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "CpbWF3ryV05Nk4JmxvIO-",
			"type": "line",
			"x": -2028.8850473933317,
			"y": -1280.0167140460817,
			"width": 21.5999755859375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2E",
			"roundness": {
				"type": 2
			},
			"seed": 226705407,
			"version": 131,
			"versionNonce": 811551633,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.5999755859375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "kt4WDwsroZwZh1RmNC6Ba",
			"type": "line",
			"x": -2011.285041289816,
			"y": -1157.6167201495973,
			"width": 31.199981689453125,
			"height": 36,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2F",
			"roundness": {
				"type": 2
			},
			"seed": 1882777631,
			"version": 111,
			"versionNonce": 1181856113,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-31.199981689453125,
					-36
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "iAr4e7m2TQ2NMTCcJmT2u",
			"type": "line",
			"x": -1997.6850046687223,
			"y": -1162.4167384601442,
			"width": 97.5999755859375,
			"height": 84.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2G",
			"roundness": {
				"type": 2
			},
			"seed": 440699967,
			"version": 153,
			"versionNonce": 486300497,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					-84.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "wEgVuEYGTDOi9ZyGWPr72",
			"type": "line",
			"x": -1844.0850290827848,
			"y": -1307.216726253113,
			"width": 81.5999755859375,
			"height": 29.600006103515625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2H",
			"roundness": {
				"type": 2
			},
			"seed": 663137375,
			"version": 135,
			"versionNonce": 72796465,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-81.5999755859375,
					-29.600006103515625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "CWVLom739ecWZ2GrABYy3",
			"type": "line",
			"x": -1823.285041289816,
			"y": -1303.216726253113,
			"width": 28.79998779296875,
			"height": 78.39999389648438,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2I",
			"roundness": {
				"type": 2
			},
			"seed": 1674561663,
			"version": 131,
			"versionNonce": 1441299217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.79998779296875,
					78.39999389648438
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "S29Y2My1LJsoYo1G4ClYD",
			"type": "line",
			"x": -1901.6850046687223,
			"y": -1247.216726253113,
			"width": 5.60003662109375,
			"height": 52.79998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2J",
			"roundness": {
				"type": 2
			},
			"seed": 1289773215,
			"version": 125,
			"versionNonce": 1378414833,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.60003662109375,
					52.79998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "j4_Gn8oshwfYvcrIYjUU-",
			"type": "line",
			"x": -1900.8850168757535,
			"y": -1248.0167140460817,
			"width": 97.5999755859375,
			"height": 30.399993896484375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2K",
			"roundness": {
				"type": 2
			},
			"seed": 1416164543,
			"version": 147,
			"versionNonce": 1050651345,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.5999755859375,
					30.399993896484375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Rkpee73Chb7V-QC-Lxuom",
			"type": "ellipse",
			"x": -1931.4297652824152,
			"y": -1291.924026941204,
			"width": 53.05265727796052,
			"height": 45.47369706003286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2L",
			"roundness": {
				"type": 2
			},
			"seed": 1644823775,
			"version": 422,
			"versionNonce": 1139026097,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "5ktosQBE",
			"type": "text",
			"x": -2012.434943633566,
			"y": -1157.4542674518434,
			"width": 21.279998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"BnGypEg_R_3dSKiRXgjWm",
				"q61zNck-lG7Z1fL70qx1P",
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2M",
			"roundness": null,
			"seed": 357830911,
			"version": 167,
			"versionNonce": 194898577,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "drcvBfPL",
			"type": "text",
			"x": -2020.8966631201529,
			"y": -1304.6627443550606,
			"width": 10.779998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2N",
			"roundness": null,
			"seed": 1204263199,
			"version": 124,
			"versionNonce": 511996017,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "AmHi7vAv",
			"type": "text",
			"x": -1936.7802290144155,
			"y": -1365.4359408231526,
			"width": 18,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2O",
			"roundness": null,
			"seed": 1322589503,
			"version": 109,
			"versionNonce": 39795281,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": false,
			"lineHeight": 1.25
		},
		{
			"id": "drfiu944",
			"type": "text",
			"x": -1837.2168859821886,
			"y": -1336.270811092555,
			"width": 10.779998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2P",
			"roundness": null,
			"seed": 2111642975,
			"version": 95,
			"versionNonce": 403032113,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "Cne5XkI2",
			"type": "text",
			"x": -1793.971990826256,
			"y": -1226.6505968875513,
			"width": 10.779998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2Q",
			"roundness": null,
			"seed": 1747982719,
			"version": 110,
			"versionNonce": 962566673,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "aIwamUtP",
			"type": "text",
			"x": -1912.6435540522389,
			"y": -1286.9920157445358,
			"width": 10.779998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2R",
			"roundness": null,
			"seed": 1661899167,
			"version": 98,
			"versionNonce": 392441841,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "fUOb4P51",
			"type": "text",
			"x": -1925.717720597646,
			"y": -1188.434348320366,
			"width": 10.779998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2S",
			"roundness": null,
			"seed": 1202259391,
			"version": 147,
			"versionNonce": 1478166993,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "PpL7FJyZ",
			"type": "text",
			"x": -2057.4631434565144,
			"y": -1227.6562341315444,
			"width": 10.779998779296875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2T",
			"roundness": null,
			"seed": 1965028831,
			"version": 142,
			"versionNonce": 1956358065,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "q",
			"rawText": "q",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "Ck3xCGah",
			"type": "text",
			"x": -2221.375353693651,
			"y": -1087.920111875725,
			"width": 716.6595458984375,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2U",
			"roundness": null,
			"seed": 310632959,
			"version": 497,
			"versionNonce": 1460504977,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "where q is a vector whose entries are probabilities over all given classes. \nEach entry is nonnegative and all entries sum up to 1",
			"rawText": "where q is a vector whose entries are probabilities over all given classes. \nEach entry is nonnegative and all entries sum up to 1",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "where q is a vector whose entries are probabilities over all given classes. \nEach entry is nonnegative and all entries sum up to 1",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "FPXkl3I0nIwQ1l_t-fF4F",
			"type": "arrow",
			"x": -1750.8641518450677,
			"y": -1244.158482295341,
			"width": 463.32752454974843,
			"height": 145.46333401343907,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2V",
			"roundness": {
				"type": 2
			},
			"seed": 282413599,
			"version": 184,
			"versionNonce": 950546289,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					463.32752454974843,
					145.46333401343907
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "h6bdMYLx",
			"type": "text",
			"x": -1643.1135137592582,
			"y": -1305.2172046130377,
			"width": 854.9595336914062,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2W",
			"roundness": null,
			"seed": 1829023295,
			"version": 381,
			"versionNonce": 1068702033,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "For each output vector, infer the index of the entry with the highest probability value.\nThe index corresponds to a specific label (or class) ",
			"rawText": "For each output vector, infer the index of the entry with the highest probability value.\nThe index corresponds to a specific label (or class) ",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For each output vector, infer the index of the entry with the highest probability value.\nThe index corresponds to a specific label (or class) ",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "k--ZJvOpPakVidP49JEqR",
			"type": "freedraw",
			"x": -4015.7963585428897,
			"y": -621.6504887486624,
			"width": 17.351635478217077,
			"height": 28.5062650398429,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2X",
			"roundness": null,
			"seed": 837979743,
			"version": 81,
			"versionNonce": 1569048369,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.478764543114039,
					0
				],
				[
					-3.718146814670945,
					1.2393822715570195
				],
				[
					-4.957529086228078,
					1.2393822715570195
				],
				[
					-4.957529086228078,
					2.478859101920193
				],
				[
					-6.197005916591479,
					4.957623645034346
				],
				[
					-7.436388188148385,
					4.957623645034346
				],
				[
					-8.67577045970529,
					6.197005916591365
				],
				[
					-8.67577045970529,
					7.436388188148385
				],
				[
					-8.67577045970529,
					8.675865018511558
				],
				[
					-9.915152731262424,
					8.675865018511558
				],
				[
					-9.915152731262424,
					9.915247290068692
				],
				[
					-9.915152731262424,
					11.154629561625711
				],
				[
					-9.915152731262424,
					12.39401183318273
				],
				[
					-9.915152731262424,
					13.633394104739864
				],
				[
					-9.915152731262424,
					14.872870935103037
				],
				[
					-9.915152731262424,
					16.112253206660057
				],
				[
					-9.915152731262424,
					17.351635478217077
				],
				[
					-9.915152731262424,
					18.59101774977421
				],
				[
					-9.915152731262424,
					19.83040002133123
				],
				[
					-8.67577045970529,
					22.309259123251422
				],
				[
					-7.436388188148385,
					22.309259123251422
				],
				[
					-6.197005916591479,
					24.788023666365575
				],
				[
					-6.197005916591479,
					26.027405937922595
				],
				[
					-4.957529086228078,
					26.027405937922595
				],
				[
					-3.718146814670945,
					27.266882768285768
				],
				[
					-3.718146814670945,
					28.5062650398429
				],
				[
					-2.478764543114039,
					28.5062650398429
				],
				[
					-1.2393822715571332,
					28.5062650398429
				],
				[
					0,
					28.5062650398429
				],
				[
					1.2394768303631736,
					28.5062650398429
				],
				[
					2.478859101920307,
					28.5062650398429
				],
				[
					3.7182413734772126,
					27.266882768285768
				],
				[
					4.957623645034346,
					24.788023666365575
				],
				[
					4.957623645034346,
					23.548641394808556
				],
				[
					4.957623645034346,
					22.309259123251422
				],
				[
					4.957623645034346,
					21.069876851694403
				],
				[
					4.957623645034346,
					19.83040002133123
				],
				[
					4.957623645034346,
					18.59101774977421
				],
				[
					4.957623645034346,
					16.112253206660057
				],
				[
					4.957623645034346,
					14.872870935103037
				],
				[
					6.197005916591479,
					12.39401183318273
				],
				[
					7.436482746954653,
					9.915247290068692
				],
				[
					7.436482746954653,
					8.675865018511558
				],
				[
					7.436482746954653,
					7.436388188148385
				],
				[
					7.436482746954653,
					6.197005916591365
				],
				[
					7.436482746954653,
					3.7182413734772126
				],
				[
					7.436482746954653,
					2.478859101920193
				],
				[
					7.436482746954653,
					1.2393822715570195
				],
				[
					7.436482746954653,
					0
				],
				[
					7.436482746954653,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "o1Tv5SpYp6AFJ_AODVhBq",
			"type": "freedraw",
			"x": -3992.2477171480814,
			"y": -595.6230828107398,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2Y",
			"roundness": null,
			"seed": 980380287,
			"version": 32,
			"versionNonce": 1820834065,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "iqKXPCnL6HmigRDE29V-X",
			"type": "freedraw",
			"x": -3979.8537053148984,
			"y": -608.0170946439225,
			"width": 2.478859101920307,
			"height": 32.224411854514074,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2Z",
			"roundness": null,
			"seed": 859554463,
			"version": 57,
			"versionNonce": 238055153,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.2393822715571332
				],
				[
					0,
					-3.7181468146711723
				],
				[
					0,
					-6.197005916591479
				],
				[
					1.2393822715571332,
					-7.436388188148499
				],
				[
					1.2393822715571332,
					-9.915152731262651
				],
				[
					2.478859101920307,
					-11.15453500281967
				],
				[
					2.478859101920307,
					-13.633394104739864
				],
				[
					2.478859101920307,
					-14.872776376296997
				],
				[
					2.478859101920307,
					-16.112158647854017
				],
				[
					2.478859101920307,
					-17.351540919411036
				],
				[
					2.478859101920307,
					-14.872776376296997
				],
				[
					2.478859101920307,
					-13.633394104739864
				],
				[
					2.478859101920307,
					-12.394011833182844
				],
				[
					2.478859101920307,
					-9.915152731262651
				],
				[
					2.478859101920307,
					-6.197005916591479
				],
				[
					2.478859101920307,
					-3.7181468146711723
				],
				[
					2.478859101920307,
					-1.2393822715571332
				],
				[
					1.2393822715571332,
					1.2394768303631736
				],
				[
					1.2393822715571332,
					3.7182413734772126
				],
				[
					1.2393822715571332,
					6.197005916591365
				],
				[
					1.2393822715571332,
					8.675865018511558
				],
				[
					1.2393822715571332,
					11.154629561625711
				],
				[
					1.2393822715571332,
					12.39401183318273
				],
				[
					1.2393822715571332,
					13.633488663545904
				],
				[
					1.2393822715571332,
					14.872870935103037
				],
				[
					1.2393822715571332,
					14.872870935103037
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "SI5vEBLT-S6W322yT9jov",
			"type": "freedraw",
			"x": -3995.9658639627523,
			"y": -567.1168177708969,
			"width": 0,
			"height": 1.2393822715570195,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2a",
			"roundness": null,
			"seed": 1560811199,
			"version": 33,
			"versionNonce": 1225222353,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.2393822715570195
				],
				[
					0,
					-1.2393822715570195
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "9i99p3cz4gQT4FGO9MwsU",
			"type": "freedraw",
			"x": -4004.6417289812634,
			"y": -568.356200042454,
			"width": 19.830400021331343,
			"height": 30.98502958295694,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2b",
			"roundness": null,
			"seed": 242542303,
			"version": 90,
			"versionNonce": 1722033841,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2393822715571332,
					0
				],
				[
					1.2393822715571332,
					-1.2393822715571332
				],
				[
					-1.2393822715571332,
					-1.2393822715571332
				],
				[
					-2.4787645431142664,
					-1.2393822715571332
				],
				[
					-3.7181468146711723,
					0
				],
				[
					-4.957623645034346,
					0
				],
				[
					-6.197005916591479,
					1.2393822715570195
				],
				[
					-7.436388188148612,
					2.478764543114039
				],
				[
					-7.436388188148612,
					3.7181468146711723
				],
				[
					-8.675770459705518,
					3.7181468146711723
				],
				[
					-9.915152731262651,
					3.7181468146711723
				],
				[
					-9.915152731262651,
					4.957623645034346
				],
				[
					-9.915152731262651,
					6.197005916591365
				],
				[
					-9.915152731262651,
					7.436388188148385
				],
				[
					-9.915152731262651,
					8.675770459705518
				],
				[
					-9.915152731262651,
					9.915152731262538
				],
				[
					-9.915152731262651,
					11.154629561625711
				],
				[
					-9.915152731262651,
					12.39401183318273
				],
				[
					-9.915152731262651,
					13.633394104739864
				],
				[
					-9.915152731262651,
					14.872776376296883
				],
				[
					-9.915152731262651,
					16.112158647853903
				],
				[
					-9.915152731262651,
					18.59101774977421
				],
				[
					-9.915152731262651,
					19.83040002133123
				],
				[
					-9.915152731262651,
					22.309164564445382
				],
				[
					-9.915152731262651,
					23.548641394808556
				],
				[
					-8.675770459705518,
					24.788023666365575
				],
				[
					-8.675770459705518,
					26.027405937922595
				],
				[
					-7.436388188148612,
					27.266788209479728
				],
				[
					-7.436388188148612,
					28.506170481036747
				],
				[
					-6.197005916591479,
					28.506170481036747
				],
				[
					-4.957623645034346,
					28.506170481036747
				],
				[
					-3.7181468146711723,
					28.506170481036747
				],
				[
					-2.4787645431142664,
					27.266788209479728
				],
				[
					-1.2393822715571332,
					26.027405937922595
				],
				[
					0,
					26.027405937922595
				],
				[
					1.2393822715571332,
					24.788023666365575
				],
				[
					1.2393822715571332,
					23.548641394808556
				],
				[
					2.4788591019200794,
					23.548641394808556
				],
				[
					3.7182413734772126,
					22.309164564445382
				],
				[
					3.7182413734772126,
					21.06978229288825
				],
				[
					4.957623645034346,
					19.83040002133123
				],
				[
					6.197005916591479,
					18.59101774977421
				],
				[
					7.436388188148385,
					17.351635478217077
				],
				[
					7.436388188148385,
					16.112158647853903
				],
				[
					8.675865018511558,
					13.633394104739864
				],
				[
					8.675865018511558,
					12.39401183318273
				],
				[
					9.915247290068692,
					11.154629561625711
				],
				[
					9.915247290068692,
					8.675770459705518
				],
				[
					9.915247290068692,
					7.436388188148385
				],
				[
					9.915247290068692,
					4.957623645034346
				],
				[
					9.915247290068692,
					3.7181468146711723
				],
				[
					9.915247290068692,
					2.478764543114039
				],
				[
					9.915247290068692,
					1.2393822715570195
				],
				[
					9.915247290068692,
					0
				],
				[
					9.915247290068692,
					-1.2393822715571332
				],
				[
					8.675865018511558,
					-1.2393822715571332
				],
				[
					8.675865018511558,
					-2.478859101920193
				],
				[
					7.436388188148385,
					-2.478859101920193
				],
				[
					7.436388188148385,
					-2.478859101920193
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "ZSWRPKgvoJLU9OViVnztU",
			"type": "freedraw",
			"x": -3984.8113289599332,
			"y": -546.0470354780086,
			"width": 2.478859101920307,
			"height": 2.478859101920193,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2c",
			"roundness": null,
			"seed": 1980936959,
			"version": 36,
			"versionNonce": 296626321,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.2394768303631736
				],
				[
					0,
					2.478859101920193
				],
				[
					1.239476830363401,
					2.478859101920193
				],
				[
					2.478859101920307,
					2.478859101920193
				],
				[
					2.478859101920307,
					2.478859101920193
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "GvFp9iV6BabCEdbsWNewc",
			"type": "freedraw",
			"x": -3966.220311210158,
			"y": -575.7925882306024,
			"width": 8.675770459705518,
			"height": 35.942558669185246,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2d",
			"roundness": null,
			"seed": 476183327,
			"version": 60,
			"versionNonce": 870116977,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2394768303629462,
					2.4787645431141527
				],
				[
					2.4788591019200794,
					2.4787645431141527
				],
				[
					2.4788591019200794,
					4.9575290862283055
				],
				[
					2.4788591019200794,
					7.436388188148499
				],
				[
					2.4788591019200794,
					8.675770459705518
				],
				[
					2.4788591019200794,
					11.15453500281967
				],
				[
					2.4788591019200794,
					13.633394104739864
				],
				[
					2.4788591019200794,
					16.112158647854017
				],
				[
					2.4788591019200794,
					17.351540919411036
				],
				[
					1.2394768303629462,
					19.83040002133123
				],
				[
					0,
					19.83040002133123
				],
				[
					0,
					21.069782292888362
				],
				[
					0,
					23.5485468360024
				],
				[
					-1.2393822715571332,
					23.5485468360024
				],
				[
					-2.4787645431142664,
					24.788023666365575
				],
				[
					-2.4787645431142664,
					26.02740593792271
				],
				[
					-3.7181468146713996,
					27.266788209479728
				],
				[
					-4.9575290862283055,
					28.506170481036747
				],
				[
					-4.9575290862283055,
					29.74555275259388
				],
				[
					-3.7181468146713996,
					29.74555275259388
				],
				[
					-2.4787645431142664,
					29.74555275259388
				],
				[
					-1.2393822715571332,
					29.74555275259388
				],
				[
					0,
					29.74555275259388
				],
				[
					1.2394768303629462,
					29.74555275259388
				],
				[
					2.4788591019200794,
					29.74555275259388
				],
				[
					3.7182413734772126,
					29.74555275259388
				],
				[
					1.2394768303629462,
					32.224411854514074
				],
				[
					-1.2393822715571332,
					35.942558669185246
				],
				[
					-1.2393822715571332,
					35.942558669185246
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "MSfnn8QBz-x1BH2wulBmI",
			"type": "freedraw",
			"x": -3983.5718521295694,
			"y": -527.4560177282342,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2e",
			"roundness": null,
			"seed": 634601279,
			"version": 32,
			"versionNonce": 335018065,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "gHA8Rr-0xRXSEplDSnsyW",
			"type": "freedraw",
			"x": -3989.768858046161,
			"y": -491.5133645002429,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2f",
			"roundness": null,
			"seed": 1422327647,
			"version": 32,
			"versionNonce": 869713457,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "_qEaAgWcqgEDAQsKe_WnB",
			"type": "freedraw",
			"x": -3989.768858046161,
			"y": -464.2464817319574,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2g",
			"roundness": null,
			"seed": 1267579775,
			"version": 32,
			"versionNonce": 1851840529,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.0001,
					0.0001
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "tOwgCT3a_6YqEwBzVQnPS",
			"type": "freedraw",
			"x": -3994.7264816911957,
			"y": -471.6829644789118,
			"width": 19.830400021331343,
			"height": 33.46388868487725,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2h",
			"roundness": null,
			"seed": 241693599,
			"version": 77,
			"versionNonce": 1435348465,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.2393822715570195
				],
				[
					-1.2393822715571332,
					-1.2393822715570195
				],
				[
					-2.478859101920307,
					-1.2393822715570195
				],
				[
					-3.7182413734772126,
					0
				],
				[
					-4.957623645034346,
					1.2394768303631736
				],
				[
					-4.957623645034346,
					2.478859101920307
				],
				[
					-6.197005916591479,
					2.478859101920307
				],
				[
					-7.436388188148612,
					4.957623645034346
				],
				[
					-7.436388188148612,
					6.197005916591479
				],
				[
					-8.675865018511558,
					7.436482746954539
				],
				[
					-9.915247290068692,
					8.675865018511672
				],
				[
					-9.915247290068692,
					11.154629561625825
				],
				[
					-9.915247290068692,
					12.394011833182844
				],
				[
					-11.154629561625825,
					13.633488663546018
				],
				[
					-11.154629561625825,
					16.112253206660057
				],
				[
					-11.154629561625825,
					17.35163547821719
				],
				[
					-11.154629561625825,
					18.59101774977421
				],
				[
					-11.154629561625825,
					19.830494580137383
				],
				[
					-11.154629561625825,
					21.069876851694403
				],
				[
					-11.154629561625825,
					23.548641394808556
				],
				[
					-11.154629561625825,
					24.788023666365575
				],
				[
					-11.154629561625825,
					26.02750049672875
				],
				[
					-11.154629561625825,
					27.266882768285882
				],
				[
					-11.154629561625825,
					29.74564731139992
				],
				[
					-11.154629561625825,
					30.985029582957054
				],
				[
					-11.154629561625825,
					32.22450641332023
				],
				[
					-9.915247290068692,
					32.22450641332023
				],
				[
					-8.675865018511558,
					32.22450641332023
				],
				[
					-7.436388188148612,
					32.22450641332023
				],
				[
					-6.197005916591479,
					30.985029582957054
				],
				[
					-4.957623645034346,
					30.985029582957054
				],
				[
					-2.478859101920307,
					28.5062650398429
				],
				[
					0,
					26.02750049672875
				],
				[
					2.478764543114039,
					23.548641394808556
				],
				[
					3.7181468146711723,
					21.069876851694403
				],
				[
					6.197005916591479,
					18.59101774977421
				],
				[
					6.197005916591479,
					16.112253206660057
				],
				[
					7.436388188148385,
					14.872870935103037
				],
				[
					7.436388188148385,
					12.394011833182844
				],
				[
					7.436388188148385,
					9.915247290068692
				],
				[
					8.675770459705518,
					8.675865018511672
				],
				[
					8.675770459705518,
					7.436482746954539
				],
				[
					8.675770459705518,
					6.197005916591479
				],
				[
					8.675770459705518,
					4.957623645034346
				],
				[
					8.675770459705518,
					3.7182413734773263
				],
				[
					8.675770459705518,
					3.7182413734773263
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "8pAcm23Kuz0RlVP4ZHbmH",
			"type": "freedraw",
			"x": -3972.4173171267503,
			"y": -443.1766994390689,
			"width": 0,
			"height": 1.2393822715570195,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2i",
			"roundness": null,
			"seed": 1166419903,
			"version": 33,
			"versionNonce": 1348782033,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.2393822715570195
				],
				[
					0,
					-1.2393822715570195
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "oDbFX5SnOtBKonKOOYkk2",
			"type": "freedraw",
			"x": -3963.7414521082383,
			"y": -476.6404935651399,
			"width": 12.39401183318273,
			"height": 33.46379412607109,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2j",
			"roundness": null,
			"seed": 1057544159,
			"version": 79,
			"versionNonce": 2029888945,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2393822715571332,
					1.2393822715570195
				],
				[
					-2.4788591019200794,
					1.2393822715570195
				],
				[
					-2.4788591019200794,
					2.4787645431141527
				],
				[
					-2.4788591019200794,
					3.7181468146711723
				],
				[
					-2.4788591019200794,
					4.957529086228192
				],
				[
					-2.4788591019200794,
					6.197005916591365
				],
				[
					-2.4788591019200794,
					7.436388188148499
				],
				[
					-3.7182413734772126,
					8.675770459705518
				],
				[
					-3.7182413734772126,
					9.915152731262538
				],
				[
					-2.4788591019200794,
					9.915152731262538
				],
				[
					-1.2393822715571332,
					9.915152731262538
				],
				[
					-1.2393822715571332,
					8.675770459705518
				],
				[
					0,
					8.675770459705518
				],
				[
					0,
					9.915152731262538
				],
				[
					1.2393822715571332,
					11.15453500281967
				],
				[
					1.2393822715571332,
					12.39401183318273
				],
				[
					2.478764543114039,
					14.872776376296883
				],
				[
					2.478764543114039,
					16.112158647854017
				],
				[
					2.478764543114039,
					17.351540919411036
				],
				[
					3.7181468146711723,
					17.351540919411036
				],
				[
					3.7181468146711723,
					18.59101774977421
				],
				[
					3.7181468146711723,
					19.83040002133123
				],
				[
					3.7181468146711723,
					21.06978229288825
				],
				[
					4.957623645034346,
					21.06978229288825
				],
				[
					4.957623645034346,
					22.309164564445382
				],
				[
					4.957623645034346,
					23.5485468360024
				],
				[
					4.957623645034346,
					24.788023666365575
				],
				[
					4.957623645034346,
					26.027405937922595
				],
				[
					4.957623645034346,
					27.266788209479728
				],
				[
					4.957623645034346,
					28.506170481036747
				],
				[
					3.7181468146711723,
					29.745552752593767
				],
				[
					3.7181468146711723,
					30.98502958295694
				],
				[
					2.478764543114039,
					30.98502958295694
				],
				[
					2.478764543114039,
					32.224411854514074
				],
				[
					1.2393822715571332,
					33.46379412607109
				],
				[
					0,
					33.46379412607109
				],
				[
					-1.2393822715571332,
					33.46379412607109
				],
				[
					-2.4788591019200794,
					33.46379412607109
				],
				[
					-4.957623645034346,
					32.224411854514074
				],
				[
					-4.957623645034346,
					30.98502958295694
				],
				[
					-4.957623645034346,
					29.745552752593767
				],
				[
					-6.197005916591479,
					29.745552752593767
				],
				[
					-6.197005916591479,
					27.266788209479728
				],
				[
					-7.436388188148385,
					26.027405937922595
				],
				[
					-7.436388188148385,
					23.5485468360024
				],
				[
					-7.436388188148385,
					22.309164564445382
				],
				[
					-7.436388188148385,
					19.83040002133123
				],
				[
					-7.436388188148385,
					19.83040002133123
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "-C9zwrbiZpbYG7OpE64CE",
			"type": "freedraw",
			"x": -3963.7414521082383,
			"y": -475.40111129358297,
			"width": 9.915152731262651,
			"height": 2.478859101920193,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2k",
			"roundness": null,
			"seed": 822117375,
			"version": 40,
			"versionNonce": 981452689,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2393822715571332,
					0
				],
				[
					2.478764543114039,
					-1.2393822715570195
				],
				[
					3.7181468146711723,
					-1.2393822715570195
				],
				[
					4.957623645034346,
					-1.2393822715570195
				],
				[
					6.197005916591479,
					-1.2393822715570195
				],
				[
					7.436388188148385,
					-1.2393822715570195
				],
				[
					8.675770459705518,
					-2.478859101920193
				],
				[
					9.915152731262651,
					-2.478859101920193
				],
				[
					9.915152731262651,
					-2.478859101920193
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "5BsPF3rcKXcKVVRDpMOh1",
			"type": "freedraw",
			"x": -3911.686640232393,
			"y": -636.5232651249594,
			"width": 13.633299545933824,
			"height": 182.19193612426466,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2l",
			"roundness": null,
			"seed": 997043231,
			"version": 123,
			"versionNonce": 790801777,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2394768303631736,
					-1.2393822715570195
				],
				[
					2.478764543114039,
					1.2393822715571332
				],
				[
					2.478764543114039,
					2.4787645431141527
				],
				[
					2.478764543114039,
					3.718146814671286
				],
				[
					2.478764543114039,
					4.957623645034346
				],
				[
					3.7182413734772126,
					7.436388188148499
				],
				[
					3.7182413734772126,
					8.675770459705518
				],
				[
					4.957718203840386,
					11.154629561625825
				],
				[
					4.957718203840386,
					13.633394104739864
				],
				[
					6.197005916591252,
					14.872776376296997
				],
				[
					6.197005916591252,
					17.35163547821719
				],
				[
					6.197005916591252,
					19.830400021331343
				],
				[
					6.197005916591252,
					23.548641394808556
				],
				[
					6.197005916591252,
					28.50617048103686
				],
				[
					6.197005916591252,
					33.46379412607121
				],
				[
					6.197005916591252,
					37.18203549954842
				],
				[
					7.436482746954425,
					39.66080004266257
				],
				[
					7.436482746954425,
					43.3790414161399
				],
				[
					7.436482746954425,
					45.85780595925394
				],
				[
					7.436482746954425,
					47.09718823081107
				],
				[
					7.436482746954425,
					48.336665061174244
				],
				[
					7.436482746954425,
					50.81542960428828
				],
				[
					7.436482746954425,
					52.05481187584542
				],
				[
					7.436482746954425,
					54.53367097776561
				],
				[
					7.436482746954425,
					57.01243552087976
				],
				[
					7.436482746954425,
					58.25181779243678
				],
				[
					7.436482746954425,
					60.730676894356975
				],
				[
					7.436482746954425,
					64.44882370902815
				],
				[
					7.436482746954425,
					66.92768281094834
				],
				[
					7.436482746954425,
					69.4064473540625
				],
				[
					7.436482746954425,
					71.88521189717665
				],
				[
					7.436482746954425,
					73.12468872753982
				],
				[
					7.436482746954425,
					75.60345327065386
				],
				[
					7.436482746954425,
					76.84283554221099
				],
				[
					7.436482746954425,
					78.08221781376801
				],
				[
					7.436482746954425,
					79.32169464413118
				],
				[
					7.436482746954425,
					80.5610769156882
				],
				[
					8.675770459705518,
					81.80045918724534
				],
				[
					8.675770459705518,
					83.03984145880236
				],
				[
					8.675770459705518,
					81.80045918724534
				],
				[
					8.675770459705518,
					83.03984145880236
				],
				[
					8.675770459705518,
					84.27922373035938
				],
				[
					7.436482746954425,
					85.51870056072255
				],
				[
					7.436482746954425,
					87.9974651038367
				],
				[
					6.197005916591252,
					89.23684737539372
				],
				[
					4.957718203840386,
					91.71570647731403
				],
				[
					3.7182413734772126,
					94.19447102042807
				],
				[
					2.478764543114039,
					96.67323556354222
				],
				[
					1.2394768303631736,
					97.9127123939054
				],
				[
					1.2394768303631736,
					100.39147693701955
				],
				[
					1.2394768303631736,
					102.87024148013359
				],
				[
					1.2394768303631736,
					104.10971831049676
				],
				[
					0,
					106.58848285361091
				],
				[
					-1.2392877127510928,
					109.06724739672507
				],
				[
					-1.2392877127510928,
					110.30672422708813
				],
				[
					-1.2392877127510928,
					112.78548877020228
				],
				[
					-1.2392877127510928,
					114.02487104175941
				],
				[
					-1.2392877127510928,
					116.5037301436796
				],
				[
					-1.2392877127510928,
					117.74311241523662
				],
				[
					-1.2392877127510928,
					120.22187695835078
				],
				[
					-1.2392877127510928,
					122.70073606027097
				],
				[
					-1.2392877127510928,
					125.17950060338512
				],
				[
					-1.2392877127510928,
					127.65826514649916
				],
				[
					-1.2392877127510928,
					130.13712424841947
				],
				[
					-1.2392877127510928,
					132.6158887915335
				],
				[
					-1.2392877127510928,
					133.85527106309064
				],
				[
					-1.2392877127510928,
					136.33413016501083
				],
				[
					-1.2392877127510928,
					137.57351243656785
				],
				[
					-1.2392877127510928,
					138.812894708125
				],
				[
					0,
					140.052276979682
				],
				[
					0,
					141.29175381004518
				],
				[
					0,
					142.5311360816022
				],
				[
					0,
					143.77051835315933
				],
				[
					0,
					146.24928289627337
				],
				[
					0,
					147.48875972663654
				],
				[
					0,
					151.20690654130772
				],
				[
					0,
					156.16453018634206
				],
				[
					0,
					158.64329472945622
				],
				[
					-1.2392877127510928,
					162.36153610293354
				],
				[
					-1.2392877127510928,
					164.84030064604758
				],
				[
					-2.4787645431142664,
					168.5585420195249
				],
				[
					-2.4787645431142664,
					169.79792429108193
				],
				[
					-2.4787645431142664,
					171.03730656263906
				],
				[
					-2.4787645431142664,
					173.51616566455925
				],
				[
					-2.4787645431142664,
					174.75554793611627
				],
				[
					-2.4787645431142664,
					175.9949302076734
				],
				[
					-3.71824137347744,
					177.23431247923043
				],
				[
					-3.71824137347744,
					178.4737893095936
				],
				[
					-4.9575290862283055,
					179.71317158115062
				],
				[
					-4.9575290862283055,
					180.95255385270764
				],
				[
					-4.9575290862283055,
					178.4737893095936
				],
				[
					-4.9575290862283055,
					178.4737893095936
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "Rq1bis6K",
			"type": "text",
			"x": -3869.546886529004,
			"y": -555.9621882092711,
			"width": 314.519775390625,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2m",
			"roundness": null,
			"seed": 708890687,
			"version": 85,
			"versionNonce": 1043191633,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "all entries are non-negative and \nsum up to 1",
			"rawText": "all entries are non-negative and \nsum up to 1",
			"fontSize": 20,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all entries are non-negative and \nsum up to 1",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "m1OPvUIMeEBympEF2uKaA",
			"type": "rectangle",
			"x": -4035.626758564221,
			"y": -490.27388766987974,
			"width": 84.27931828916553,
			"height": 58.25181779243667,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2n",
			"roundness": {
				"type": 3
			},
			"seed": 2002415711,
			"version": 255,
			"versionNonce": 2046346545,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "drWmROMkOKsFAJGtBmKNE",
			"type": "arrow",
			"x": -4076.5269408784407,
			"y": -445.65546398218294,
			"width": 210.69820116410756,
			"height": 106.58853013301393,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2o",
			"roundness": {
				"type": 2
			},
			"seed": 210439295,
			"version": 111,
			"versionNonce": 1038808849,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-210.69820116410756,
					-106.58853013301393
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "49tadH25",
			"type": "text",
			"x": -4466.938408182505,
			"y": -626.6080651142938,
			"width": 399.8052978515625,
			"height": 61.36655861585698,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2p",
			"roundness": null,
			"seed": 1167271071,
			"version": 363,
			"versionNonce": 209448177,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "the K-th entry is the highest value,\nso the K-end member is the class for this vector, \nand the one-hot pseudo-labeling is q",
			"rawText": "the K-th entry is the highest value,\nso the K-end member is the class for this vector, \nand the one-hot pseudo-labeling is q",
			"fontSize": 16.364415630895195,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the K-th entry is the highest value,\nso the K-end member is the class for this vector, \nand the one-hot pseudo-labeling is q",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "OWHNxFpJ8BEq_tZIluVXI",
			"type": "freedraw",
			"x": -4033.147899462301,
			"y": -1277.2937099960923,
			"width": 23.548546836002515,
			"height": 38.42144141080698,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2q",
			"roundness": null,
			"seed": 841169087,
			"version": 62,
			"versionNonce": 758326993,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2393822715571332,
					0
				],
				[
					2.4787645431142664,
					0
				],
				[
					3.7181468146713996,
					0
				],
				[
					4.9575290862283055,
					0
				],
				[
					6.197005916591479,
					0
				],
				[
					8.675770459705745,
					-1.2394059112585865
				],
				[
					11.154535002819557,
					-4.957600005332836
				],
				[
					13.633394104740091,
					-7.436411827850009
				],
				[
					17.351540919411036,
					-11.15460592192423
				],
				[
					19.830400021331343,
					-13.633417744441402
				],
				[
					21.06978229288825,
					-16.112205927257037
				],
				[
					22.309164564445382,
					-16.112205927257037
				],
				[
					23.548546836002515,
					-16.112205927257037
				],
				[
					23.548546836002515,
					-17.351611838515623
				],
				[
					23.548546836002515,
					-16.112205927257037
				],
				[
					23.548546836002515,
					-13.633417744441402
				],
				[
					23.548546836002515,
					-11.15460592192423
				],
				[
					22.309164564445382,
					-7.436411827850009
				],
				[
					22.309164564445382,
					-3.7181940940742493
				],
				[
					22.309164564445382,
					0
				],
				[
					22.309164564445382,
					3.718194094074221
				],
				[
					22.309164564445382,
					7.43641182784998
				],
				[
					22.309164564445382,
					11.154605921924201
				],
				[
					21.06978229288825,
					13.633417744441374
				],
				[
					21.06978229288825,
					14.87282365569996
				],
				[
					21.06978229288825,
					16.11220592725701
				],
				[
					21.06978229288825,
					17.351611838515595
				],
				[
					21.06978229288825,
					18.59101774977418
				],
				[
					21.06978229288825,
					19.830423661032768
				],
				[
					21.06978229288825,
					21.069829572291354
				],
				[
					21.06978229288825,
					21.069829572291354
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "fI1lhVbiRxmyHalRHp3vu",
			"type": "freedraw",
			"x": -4025.711511274152,
			"y": -1252.5056863297264,
			"width": 27.266788209479728,
			"height": 0,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2r",
			"roundness": null,
			"seed": 400279775,
			"version": 47,
			"versionNonce": 178791601,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2393822715571332,
					0
				],
				[
					2.478764543114039,
					0
				],
				[
					4.957623645034346,
					0
				],
				[
					7.436388188148385,
					0
				],
				[
					8.67577045970529,
					0
				],
				[
					11.154629561625597,
					0
				],
				[
					12.39401183318273,
					0
				],
				[
					13.633394104739637,
					0
				],
				[
					17.351635478217077,
					0
				],
				[
					19.830400021331116,
					0
				],
				[
					22.309164564445382,
					0
				],
				[
					23.548641394808328,
					0
				],
				[
					24.78802366636546,
					0
				],
				[
					26.027405937922595,
					0
				],
				[
					27.266788209479728,
					0
				],
				[
					27.266788209479728,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "57Jz9inpIen_Xccw77oWN",
			"type": "freedraw",
			"x": -4009.5993526262982,
			"y": -1178.1415916909282,
			"width": 34.70317639762834,
			"height": 49.57604733273121,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2s",
			"roundness": null,
			"seed": 877483263,
			"version": 104,
			"versionNonce": 1350723217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.478811822517173
				],
				[
					0,
					-3.7182413734772695
				],
				[
					1.2394768303631736,
					-3.7182413734772695
				],
				[
					-1.2393822715571332,
					-3.7182413734772695
				],
				[
					-2.4787645431142664,
					-2.478811822517173
				],
				[
					-4.9575290862283055,
					-1.2394295509600965
				],
				[
					-6.197005916591479,
					-1.2394295509600965
				],
				[
					-7.436388188148612,
					-1.2394295509600965
				],
				[
					-7.436388188148612,
					0
				],
				[
					-8.675770459705518,
					0
				],
				[
					-11.154535002819557,
					1.2393822715570764
				],
				[
					-12.394011833182958,
					2.478764543114096
				],
				[
					-13.633394104739864,
					4.957576365631269
				],
				[
					-16.112158647853903,
					6.197005916591422
				],
				[
					-17.351540919411036,
					7.436388188148442
				],
				[
					-18.59101774977421,
					7.436388188148442
				],
				[
					-19.830400021331116,
					9.915200010665615
				],
				[
					-19.830400021331116,
					11.154582282222691
				],
				[
					-21.06978229288825,
					11.154582282222691
				],
				[
					-21.06978229288825,
					12.394011833182788
				],
				[
					-22.309164564445382,
					13.633394104739864
				],
				[
					-23.548546836002515,
					14.87277637629694
				],
				[
					-23.548546836002515,
					16.112205927257037
				],
				[
					-23.548546836002515,
					17.351588198814113
				],
				[
					-23.548546836002515,
					18.59101774977421
				],
				[
					-23.548546836002515,
					19.830400021331286
				],
				[
					-23.548546836002515,
					22.30921184384846
				],
				[
					-23.548546836002515,
					26.02740593792265
				],
				[
					-23.548546836002515,
					28.506217760439824
				],
				[
					-23.548546836002515,
					30.985029582956997
				],
				[
					-23.548546836002515,
					32.224411854514074
				],
				[
					-23.548546836002515,
					34.70322367703125
				],
				[
					-23.548546836002515,
					37.18203549954842
				],
				[
					-22.309164564445382,
					38.42141777110544
				],
				[
					-21.06978229288825,
					39.660800042662515
				],
				[
					-21.06978229288825,
					40.90022959362261
				],
				[
					-21.06978229288825,
					42.13961186517969
				],
				[
					-19.830400021331116,
					42.13961186517969
				],
				[
					-18.59101774977421,
					43.379041416139785
				],
				[
					-18.59101774977421,
					44.61842368769686
				],
				[
					-17.351540919411036,
					44.61842368769686
				],
				[
					-16.112158647853903,
					44.61842368769686
				],
				[
					-14.87277637629677,
					44.61842368769686
				],
				[
					-13.633394104739864,
					45.85780595925394
				],
				[
					-12.394011833182958,
					45.85780595925394
				],
				[
					-9.915152731262424,
					45.85780595925394
				],
				[
					-7.436388188148612,
					43.379041416139785
				],
				[
					-4.9575290862283055,
					42.13961186517969
				],
				[
					-2.4787645431142664,
					39.660800042662515
				],
				[
					-1.2393822715571332,
					37.18203549954842
				],
				[
					0,
					34.70322367703125
				],
				[
					2.4788591019200794,
					33.46379412607109
				],
				[
					3.7182413734772126,
					30.985029582956997
				],
				[
					4.957623645034346,
					29.7456000319969
				],
				[
					6.197005916591479,
					28.506217760439824
				],
				[
					6.197005916591479,
					27.266788209479728
				],
				[
					7.436482746954425,
					23.54859411540548
				],
				[
					8.675865018511558,
					22.30921184384846
				],
				[
					8.675865018511558,
					21.069782292888306
				],
				[
					9.915247290068692,
					18.59101774977421
				],
				[
					11.154629561625825,
					16.112205927257037
				],
				[
					11.154629561625825,
					14.87277637629694
				],
				[
					11.154629561625825,
					12.394011833182788
				],
				[
					11.154629561625825,
					11.154582282222691
				],
				[
					11.154629561625825,
					8.675770459705518
				],
				[
					11.154629561625825,
					7.436388188148442
				],
				[
					11.154629561625825,
					6.197005916591422
				],
				[
					11.154629561625825,
					4.957576365631269
				],
				[
					9.915247290068692,
					3.7181940940742493
				],
				[
					9.915247290068692,
					2.478764543114096
				],
				[
					9.915247290068692,
					1.2393822715570764
				],
				[
					8.675865018511558,
					1.2393822715570764
				],
				[
					8.675865018511558,
					1.2393822715570764
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "nmmaRjE0ke5pOGh2-qRdV",
			"type": "freedraw",
			"x": -3704.7066804417627,
			"y": -1323.1515632347491,
			"width": 13.633299545933824,
			"height": 45.857853238656986,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2t",
			"roundness": null,
			"seed": 1056464159,
			"version": 67,
			"versionNonce": 1232694385,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2392877127508655,
					0
				],
				[
					0,
					-1.239382271557048
				],
				[
					0,
					-2.4787881828156344
				],
				[
					1.2394768303631736,
					-3.718194094074221
				],
				[
					3.71824137347744,
					-6.197005916591394
				],
				[
					4.957718203840614,
					-9.915200010665615
				],
				[
					6.197005916591479,
					-11.154605921924201
				],
				[
					8.675959577317826,
					-14.872800015998422
				],
				[
					8.675959577317826,
					-17.351611838515595
				],
				[
					9.915247290068692,
					-18.59101774977418
				],
				[
					11.154724120431865,
					-19.830400021331258
				],
				[
					11.154724120431865,
					-21.069805932589844
				],
				[
					12.394011833182958,
					-21.069805932589844
				],
				[
					12.394011833182958,
					-22.30921184384843
				],
				[
					12.394011833182958,
					-21.069805932589844
				],
				[
					12.394011833182958,
					-19.830400021331258
				],
				[
					12.394011833182958,
					-18.59101774977418
				],
				[
					12.394011833182958,
					-17.351611838515595
				],
				[
					12.394011833182958,
					-16.11220592725701
				],
				[
					12.394011833182958,
					-14.872800015998422
				],
				[
					12.394011833182958,
					-12.394011833182788
				],
				[
					12.394011833182958,
					-8.675794099407028
				],
				[
					12.394011833182958,
					-3.718194094074221
				],
				[
					12.394011833182958,
					0
				],
				[
					12.394011833182958,
					2.478811822517173
				],
				[
					12.394011833182958,
					6.197005916591422
				],
				[
					12.394011833182958,
					11.15462956162574
				],
				[
					12.394011833182958,
					13.633417744441402
				],
				[
					12.394011833182958,
					16.112229566958575
				],
				[
					12.394011833182958,
					18.59101774977421
				],
				[
					11.154724120431865,
					19.830423661032796
				],
				[
					11.154724120431865,
					21.069829572291383
				],
				[
					11.154724120431865,
					22.30923548354997
				],
				[
					11.154724120431865,
					23.548641394808556
				],
				[
					11.154724120431865,
					23.548641394808556
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "7NB2d0awJth6dWFt14zyw",
			"type": "freedraw",
			"x": -3707.185444984877,
			"y": -1298.3635395683837,
			"width": 37.18203549954842,
			"height": 1.239382271557048,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2u",
			"roundness": null,
			"seed": 726491455,
			"version": 48,
			"versionNonce": 2102703697,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2394768303631736,
					0
				],
				[
					2.478764543114039,
					0
				],
				[
					4.957718203840386,
					0
				],
				[
					7.436482746954653,
					0
				],
				[
					9.915247290068692,
					0
				],
				[
					12.39401183318273,
					0
				],
				[
					17.351730037023344,
					-1.239382271557048
				],
				[
					21.06978229288825,
					-1.239382271557048
				],
				[
					24.78802366636569,
					-1.239382271557048
				],
				[
					29.745741870206075,
					-1.239382271557048
				],
				[
					32.224506413320114,
					-1.239382271557048
				],
				[
					33.46379412607121,
					-1.239382271557048
				],
				[
					34.70327095643438,
					-1.239382271557048
				],
				[
					35.942747786797554,
					-1.239382271557048
				],
				[
					37.18203549954842,
					-1.239382271557048
				],
				[
					37.18203549954842,
					-1.239382271557048
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "ayXYqKcFrJc0O08sfA4Wd",
			"type": "freedraw",
			"x": -3691.073191778217,
			"y": -1285.9695277352007,
			"width": 14.872965493909305,
			"height": 23.548641394808556,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2v",
			"roundness": null,
			"seed": 715972959,
			"version": 77,
			"versionNonce": 250332209,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.2394768303631736,
					0
				],
				[
					-2.4787645431142664,
					0
				],
				[
					-3.71824137347744,
					0
				],
				[
					-4.9575290862283055,
					1.2394059112585865
				],
				[
					-6.197005916591479,
					1.2394059112585865
				],
				[
					-6.197005916591479,
					2.478811822517173
				],
				[
					-7.436482746954653,
					2.478811822517173
				],
				[
					-8.675770459705518,
					3.7182177337757594
				],
				[
					-9.915247290068692,
					4.957623645034346
				],
				[
					-11.154535002819784,
					6.197005916591422
				],
				[
					-12.394011833182958,
					7.436411827850009
				],
				[
					-12.394011833182958,
					8.675817739108595
				],
				[
					-12.394011833182958,
					9.915223650367153
				],
				[
					-13.633488663546132,
					11.15462956162574
				],
				[
					-13.633488663546132,
					12.394011833182816
				],
				[
					-13.633488663546132,
					13.633417744441402
				],
				[
					-13.633488663546132,
					14.872823655699989
				],
				[
					-13.633488663546132,
					16.112229566958575
				],
				[
					-13.633488663546132,
					17.351635478217162
				],
				[
					-13.633488663546132,
					18.59101774977421
				],
				[
					-13.633488663546132,
					19.830423661032796
				],
				[
					-12.394011833182958,
					21.069829572291383
				],
				[
					-11.154535002819784,
					22.30923548354997
				],
				[
					-9.915247290068692,
					23.548641394808556
				],
				[
					-7.436482746954653,
					23.548641394808556
				],
				[
					-6.197005916591479,
					23.548641394808556
				],
				[
					-3.71824137347744,
					23.548641394808556
				],
				[
					-2.4787645431142664,
					23.548641394808556
				],
				[
					-1.2394768303631736,
					22.30923548354997
				],
				[
					-1.2394768303631736,
					21.069829572291383
				],
				[
					0,
					21.069829572291383
				],
				[
					1.2394768303631736,
					19.830423661032796
				],
				[
					1.2394768303631736,
					18.59101774977421
				],
				[
					1.2394768303631736,
					17.351635478217162
				],
				[
					1.2394768303631736,
					16.112229566958575
				],
				[
					1.2394768303631736,
					14.872823655699989
				],
				[
					1.2394768303631736,
					13.633417744441402
				],
				[
					1.2394768303631736,
					12.394011833182816
				],
				[
					1.2394768303631736,
					11.15462956162574
				],
				[
					1.2394768303631736,
					9.915223650367153
				],
				[
					1.2394768303631736,
					7.436411827850009
				],
				[
					1.2394768303631736,
					6.197005916591422
				],
				[
					1.2394768303631736,
					4.957623645034346
				],
				[
					1.2394768303631736,
					3.7182177337757594
				],
				[
					1.2394768303631736,
					3.7182177337757594
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "2lD_D0qzkghAkV3id8AuA",
			"type": "freedraw",
			"x": -3693.551956321331,
			"y": -1178.1415916909282,
			"width": 21.069782292888476,
			"height": 34.70322367703125,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2w",
			"roundness": null,
			"seed": 1852267903,
			"version": 90,
			"versionNonce": 1512445457,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.2394295509600965
				],
				[
					1.2392877127510928,
					-1.2394295509600965
				],
				[
					1.2392877127510928,
					-2.478811822517173
				],
				[
					0,
					-1.2394295509600965
				],
				[
					-1.2394768303631736,
					-1.2394295509600965
				],
				[
					-2.478764543114039,
					0
				],
				[
					-3.7182413734772126,
					2.478764543114096
				],
				[
					-4.957718203840386,
					2.478764543114096
				],
				[
					-6.197005916591252,
					3.7181940940742493
				],
				[
					-7.436482746954425,
					4.957576365631269
				],
				[
					-7.436482746954425,
					6.197005916591422
				],
				[
					-7.436482746954425,
					7.436388188148442
				],
				[
					-7.436482746954425,
					8.675770459705518
				],
				[
					-8.675770459705518,
					11.154582282222691
				],
				[
					-8.675770459705518,
					12.394011833182788
				],
				[
					-9.915247290068692,
					14.87277637629694
				],
				[
					-9.915247290068692,
					17.351588198814113
				],
				[
					-9.915247290068692,
					18.59101774977421
				],
				[
					-9.915247290068692,
					19.830400021331286
				],
				[
					-9.915247290068692,
					21.069782292888306
				],
				[
					-9.915247290068692,
					22.30921184384846
				],
				[
					-9.915247290068692,
					23.54859411540548
				],
				[
					-9.915247290068692,
					24.788023666365575
				],
				[
					-9.915247290068692,
					27.266788209479728
				],
				[
					-8.675770459705518,
					27.266788209479728
				],
				[
					-8.675770459705518,
					28.506217760439824
				],
				[
					-8.675770459705518,
					29.7456000319969
				],
				[
					-7.436482746954425,
					29.7456000319969
				],
				[
					-6.197005916591252,
					29.7456000319969
				],
				[
					-4.957718203840386,
					29.7456000319969
				],
				[
					-3.7182413734772126,
					28.506217760439824
				],
				[
					-2.478764543114039,
					28.506217760439824
				],
				[
					-1.2394768303631736,
					27.266788209479728
				],
				[
					1.2392877127510928,
					26.02740593792265
				],
				[
					2.4787645431142664,
					24.788023666365575
				],
				[
					3.71824137347744,
					24.788023666365575
				],
				[
					4.9575290862283055,
					23.54859411540548
				],
				[
					6.197005916591479,
					22.30921184384846
				],
				[
					7.4362936293423445,
					22.30921184384846
				],
				[
					8.675770459705518,
					21.069782292888306
				],
				[
					8.675770459705518,
					19.830400021331286
				],
				[
					9.915247290068692,
					18.59101774977421
				],
				[
					9.915247290068692,
					17.351588198814113
				],
				[
					9.915247290068692,
					16.112205927257037
				],
				[
					11.154535002819784,
					13.633394104739864
				],
				[
					11.154535002819784,
					12.394011833182788
				],
				[
					11.154535002819784,
					9.915200010665615
				],
				[
					11.154535002819784,
					7.436388188148442
				],
				[
					11.154535002819784,
					6.197005916591422
				],
				[
					11.154535002819784,
					3.7181940940742493
				],
				[
					11.154535002819784,
					2.478764543114096
				],
				[
					11.154535002819784,
					0
				],
				[
					11.154535002819784,
					-1.2394295509600965
				],
				[
					11.154535002819784,
					-2.478811822517173
				],
				[
					11.154535002819784,
					-3.7182413734772695
				],
				[
					9.915247290068692,
					-4.957623645034346
				],
				[
					8.675770459705518,
					-4.957623645034346
				],
				[
					8.675770459705518,
					-4.957623645034346
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "G-1rSvoyHzEd24McB6shN",
			"type": "rectangle",
			"x": -5090.905072214542,
			"y": -2325.4816845682312,
			"width": 4861.383295917671,
			"height": 2386.697061925259,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2x",
			"roundness": {
				"type": 3
			},
			"seed": 700274079,
			"version": 177,
			"versionNonce": 1375415281,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "cdDBf1MM",
			"type": "text",
			"x": -4375.996615458391,
			"y": -2143.006314689134,
			"width": 3346.985107421875,
			"height": 165.98469202886884,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2y",
			"roundness": null,
			"seed": 1407142335,
			"version": 267,
			"versionNonce": 510821841,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "Graph-based Active Learning to Pick Training Pixels",
			"rawText": "Graph-based Active Learning to Pick Training Pixels",
			"fontSize": 132.78775362309506,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph-based Active Learning to Pick Training Pixels",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "es1y6P1MBpcNiWOMyj30f",
			"type": "rectangle",
			"x": -2379.7488823094536,
			"y": -1891.0371404131265,
			"width": 1050.3666508078388,
			"height": 329.95813656142377,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b2z",
			"roundness": {
				"type": 3
			},
			"seed": 703445471,
			"version": 138,
			"versionNonce": 2057544625,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "PiKVpVcFnmYt91vhM_zPq",
			"type": "arrow",
			"x": -1279.8884271047073,
			"y": -1759.0540116575971,
			"width": 2001.7461123853307,
			"height": 412.4475658109129,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b30",
			"roundness": {
				"type": 2
			},
			"seed": 1895376383,
			"version": 153,
			"versionNonce": 1387660689,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2001.7461123853307,
					-412.4475658109129
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "pgQjkZ3vqSSO1Cn7Uppmv",
			"type": "line",
			"x": 1684.8731077710177,
			"y": -2154.801937464419,
			"width": 146.2857491629461,
			"height": 2.2857666015625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b31",
			"roundness": {
				"type": 2
			},
			"seed": 2013400607,
			"version": 115,
			"versionNonce": 568404849,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					146.2857491629461,
					2.2857666015625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "guc3ftDTuFMWYidtgfVuk",
			"type": "line",
			"x": 1758.0158951594103,
			"y": -2218.801920025803,
			"width": 0,
			"height": 148.57142857142867,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b32",
			"roundness": {
				"type": 2
			},
			"seed": 1509487167,
			"version": 150,
			"versionNonce": 275551569,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					148.57142857142867
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "cJ6mFZ04-w6JP9964u5bh",
			"type": "line",
			"x": 903.1588918111961,
			"y": -2264.516205740089,
			"width": 1222.8571428571436,
			"height": 18.285696847098052,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dotted",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b33",
			"roundness": {
				"type": 2
			},
			"seed": 2143179359,
			"version": 190,
			"versionNonce": 1370473265,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1222.8571428571436,
					-18.285696847098052
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Hct0v6FGG99CGDbgCJ9w0",
			"type": "line",
			"x": 1374.0159997911069,
			"y": -2355.9447771686605,
			"width": 1243.4286063058034,
			"height": 93.71425083705367,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dotted",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b34",
			"roundness": {
				"type": 2
			},
			"seed": 1646440063,
			"version": 185,
			"versionNonce": 1108489489,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1243.4286063058034,
					-93.71425083705367
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "4Pd5SBl5OVxLO5ry3Vncq",
			"type": "line",
			"x": 962.5874283625353,
			"y": -1855.3733137199993,
			"width": 1186.2857491629466,
			"height": 25.142822265625,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dotted",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b35",
			"roundness": {
				"type": 2
			},
			"seed": 199657119,
			"version": 110,
			"versionNonce": 1158376177,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1186.2857491629466,
					-25.142822265625
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "a5vnBhpj",
			"type": "text",
			"x": 1762.9700431062101,
			"y": -2474.759641658125,
			"width": 376.5205078125,
			"height": 62.2627248796791,
			"angle": 6.203027656840735,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dotted",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b36",
			"roundness": null,
			"seed": 1538939583,
			"version": 167,
			"versionNonce": 1663231185,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"text": "duplicate nodes",
			"rawText": "duplicate nodes",
			"fontSize": 49.810179903743276,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "duplicate nodes",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "qtbqoqbiXDQidFOW5fWOZ",
			"type": "arrow",
			"x": 3219.92068612853,
			"y": -2188.0875471184377,
			"width": 1344.000651041666,
			"height": 10.666707356770758,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b37",
			"roundness": {
				"type": 2
			},
			"seed": 104770271,
			"version": 139,
			"versionNonce": 670048945,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1344.000651041666,
					10.666707356770758
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "fhg4Tg_x3uIFIcqcNsVtj",
			"type": "ellipse",
			"x": 4886.290766504815,
			"y": -1989.8549511325778,
			"width": 139.14542157148824,
			"height": 119.26748013168817,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b38",
			"roundness": {
				"type": 2
			},
			"seed": 1476654847,
			"version": 663,
			"versionNonce": 1075487889,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jDtxhwQFaQjeKpyXSVTEV",
					"type": "arrow"
				}
			],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "WCOi3Jo4s4XPnR8NPept6",
			"type": "ellipse",
			"x": 5736.671684008535,
			"y": -2060.616757075658,
			"width": 139.14542157148824,
			"height": 119.26748013168817,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b39",
			"roundness": {
				"type": 2
			},
			"seed": 931839775,
			"version": 912,
			"versionNonce": 913667153,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "YHd55HfPYeFzp63SoJSW0",
					"type": "arrow"
				},
				{
					"id": "I0j-ziY7SyWew44M2QbbA",
					"type": "arrow"
				},
				{
					"id": "qkSp1R8JrEy3RZKqncsIC",
					"type": "arrow"
				}
			],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "MjOxlEPtuFGqKuBAPbAtf",
			"type": "ellipse",
			"x": 4782.642644468784,
			"y": -2154.587759517879,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3A",
			"roundness": {
				"type": 2
			},
			"seed": 1732477759,
			"version": 683,
			"versionNonce": 977552337,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jDtxhwQFaQjeKpyXSVTEV",
					"type": "arrow"
				},
				{
					"id": "K4zbgTOUn_mlb9lBzwlnG",
					"type": "arrow"
				},
				{
					"id": "-JvwGSW4sHEa1W0QyOG_8",
					"type": "arrow"
				},
				{
					"id": "aDCv-acCWlewaY2lVCiNf",
					"type": "arrow"
				},
				{
					"id": "WNWSUyF5Y1iin5GuvBV5m",
					"type": "arrow"
				}
			],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "iHW8EUqsAYmQ2NSUYN-TY",
			"type": "ellipse",
			"x": 5462.467041096774,
			"y": -2150.3912963204903,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3B",
			"roundness": {
				"type": 2
			},
			"seed": 126796639,
			"version": 681,
			"versionNonce": 1895658257,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1N-14HZvd0v2iEb0mO-Tn",
					"type": "arrow"
				},
				{
					"id": "S-DLsKJHpdspHFJZzEXA_",
					"type": "arrow"
				},
				{
					"id": "HfCrGZJyGHJtgNJMkIhZA",
					"type": "arrow"
				}
			],
			"updated": 1735665508773,
			"link": null,
			"locked": false
		},
		{
			"id": "S3ejaZiJAQR1svjaVVzKy",
			"type": "ellipse",
			"x": 4862.375205096536,
			"y": -2386.4414106932854,
			"width": 100.7147965738159,
			"height": 107.00937130858179,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3C",
			"roundness": {
				"type": 2
			},
			"seed": 1488781183,
			"version": 765,
			"versionNonce": 1484186257,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "_8sQNlpi_K6CMLUI2BPN5",
					"type": "arrow"
				},
				{
					"id": "LhZpvSiYvz7nF09LuGVCa",
					"type": "arrow"
				},
				{
					"id": "WNWSUyF5Y1iin5GuvBV5m",
					"type": "arrow"
				},
				{
					"id": "VCy8mhzBLEeam9dDNKBQs",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "-5pg1LxJN16q5n7eaONBt",
			"type": "ellipse",
			"x": 5648.756285360672,
			"y": -2323.8700867535536,
			"width": 100.7147965738159,
			"height": 107.00937130858179,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3D",
			"roundness": {
				"type": 2
			},
			"seed": 1024374687,
			"version": 1002,
			"versionNonce": 1705125873,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "I0j-ziY7SyWew44M2QbbA",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "-ecAFwcwwQhzR32eu_1mJ",
			"type": "ellipse",
			"x": 5082.688602489343,
			"y": -2513.383962179244,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3E",
			"roundness": {
				"type": 2
			},
			"seed": 2058644415,
			"version": 683,
			"versionNonce": 1438359473,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "_8sQNlpi_K6CMLUI2BPN5",
					"type": "arrow"
				},
				{
					"id": "nbxDAIZ_Uki2CembX1M_7",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "yIVyOGlPXTWn1ZdYUWgvj",
			"type": "ellipse",
			"x": 5118.358339564951,
			"y": -2060.167697760585,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3F",
			"roundness": {
				"type": 2
			},
			"seed": 1036950495,
			"version": 684,
			"versionNonce": 271978833,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "K4zbgTOUn_mlb9lBzwlnG",
					"type": "arrow"
				},
				{
					"id": "1N-14HZvd0v2iEb0mO-Tn",
					"type": "arrow"
				},
				{
					"id": "aDCv-acCWlewaY2lVCiNf",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "k2xFp5l2jI8eSYLDo9S9H",
			"type": "ellipse",
			"x": 5340.77016865865,
			"y": -2439.9461363680157,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3G",
			"roundness": {
				"type": 2
			},
			"seed": 1517144063,
			"version": 686,
			"versionNonce": 609116369,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "nbxDAIZ_Uki2CembX1M_7",
					"type": "arrow"
				},
				{
					"id": "qkSp1R8JrEy3RZKqncsIC",
					"type": "arrow"
				},
				{
					"id": "HfCrGZJyGHJtgNJMkIhZA",
					"type": "arrow"
				},
				{
					"id": "VCy8mhzBLEeam9dDNKBQs",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "G3rsBYo1qxa9003uReIoR",
			"type": "ellipse",
			"x": 5396.484745016534,
			"y": -1913.3747717381798,
			"width": 100.7147965738159,
			"height": 90.22359855990517,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3H",
			"roundness": {
				"type": 2
			},
			"seed": 1318219807,
			"version": 1066,
			"versionNonce": 1271053873,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "TxccLFfO3aNKn1MeERijE",
					"type": "arrow"
				},
				{
					"id": "YHd55HfPYeFzp63SoJSW0",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "itk7MM0rbqszm3I2hXXM_",
			"type": "ellipse",
			"x": 5140.069732664937,
			"y": -2321.1534134388717,
			"width": 139.14542157148824,
			"height": 119.26748013168817,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3I",
			"roundness": {
				"type": 2
			},
			"seed": 70063167,
			"version": 915,
			"versionNonce": 993247185,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "LhZpvSiYvz7nF09LuGVCa",
					"type": "arrow"
				},
				{
					"id": "-JvwGSW4sHEa1W0QyOG_8",
					"type": "arrow"
				},
				{
					"id": "S-DLsKJHpdspHFJZzEXA_",
					"type": "arrow"
				}
			],
			"updated": 1735665508774,
			"link": null,
			"locked": false
		},
		{
			"id": "lR94zyFo",
			"type": "text",
			"x": 4922.305892607417,
			"y": -1968.4688857868196,
			"width": 55.80677795410156,
			"height": 65.56948733145406,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3J",
			"roundness": null,
			"seed": 1394488415,
			"version": 656,
			"versionNonce": 767610705,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"text": "q*",
			"rawText": "q*",
			"fontSize": 52.45558986516325,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "q*",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "_8sQNlpi_K6CMLUI2BPN5",
			"type": "arrow",
			"x": 5086.587352795194,
			"y": -2454.754417235627,
			"width": 175.999755859375,
			"height": 74.666748046875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3K",
			"roundness": {
				"type": 2
			},
			"seed": 1127633023,
			"version": 121,
			"versionNonce": 175990623,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508929,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-175.999755859375,
					74.666748046875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "-ecAFwcwwQhzR32eu_1mJ",
				"focus": 0.124052061047822,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "S3ejaZiJAQR1svjaVVzKy",
				"focus": -0.8342150823473392,
				"gap": 1,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "nbxDAIZ_Uki2CembX1M_7",
			"type": "arrow",
			"x": 5187.9207675087355,
			"y": -2476.0876284986475,
			"width": 160,
			"height": 63.99983723958326,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3L",
			"roundness": {
				"type": 2
			},
			"seed": 238413983,
			"version": 120,
			"versionNonce": 1201953695,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508929,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					160,
					63.99983723958326
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "-ecAFwcwwQhzR32eu_1mJ",
				"focus": -0.6024810790508046,
				"gap": 5.191172422076278,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "k2xFp5l2jI8eSYLDo9S9H",
				"focus": -0.0005914767324463272,
				"gap": 1,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "LhZpvSiYvz7nF09LuGVCa",
			"type": "arrow",
			"x": 5145.254344982694,
			"y": -2241.4210839022935,
			"width": 186.66666666666697,
			"height": 47.9998779296875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3M",
			"roundness": {
				"type": 2
			},
			"seed": 1640856767,
			"version": 109,
			"versionNonce": 1380663263,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-186.66666666666697,
					-47.9998779296875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "itk7MM0rbqszm3I2hXXM_",
				"focus": -0.588753877692261,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "S3ejaZiJAQR1svjaVVzKy",
				"focus": 0.5762920355278255,
				"gap": 11.42173959550474,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "jDtxhwQFaQjeKpyXSVTEV",
			"type": "arrow",
			"x": 4883.920930269152,
			"y": -2124.087709878856,
			"width": 80,
			"height": 133.33333333333348,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3N",
			"roundness": {
				"type": 2
			},
			"seed": 1637715167,
			"version": 192,
			"versionNonce": 1597379615,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					80,
					133.33333333333348
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "MjOxlEPtuFGqKuBAPbAtf",
				"focus": -1.0440293333538884,
				"gap": 3.0774257391358333,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "fhg4Tg_x3uIFIcqcNsVtj",
				"focus": 0.5672373447805275,
				"gap": 1.2943560064788002,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "K4zbgTOUn_mlb9lBzwlnG",
			"type": "arrow",
			"x": 4883.920930269152,
			"y": -2134.754417235627,
			"width": 303.99983723958303,
			"height": 64.00004069010424,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3O",
			"roundness": {
				"type": 2
			},
			"seed": 1765185791,
			"version": 257,
			"versionNonce": 1109973087,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					303.99983723958303,
					64.00004069010424
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "MjOxlEPtuFGqKuBAPbAtf",
				"focus": -0.7768245988490056,
				"gap": 7.646450584027107,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "yIVyOGlPXTWn1ZdYUWgvj",
				"focus": 1.2891809184368344,
				"gap": 13.30315778295936,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "-JvwGSW4sHEa1W0QyOG_8",
			"type": "arrow",
			"x": 5155.920848888944,
			"y": -2220.087669188752,
			"width": 266.66666666666697,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3P",
			"roundness": {
				"type": 2
			},
			"seed": 236527903,
			"version": 137,
			"versionNonce": 770149535,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-266.66666666666697,
					80
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "itk7MM0rbqszm3I2hXXM_",
				"focus": -0.4006837410215605,
				"gap": 2.5009542488316896,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "MjOxlEPtuFGqKuBAPbAtf",
				"focus": -0.28871684971261397,
				"gap": 14.99152822492482,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "1N-14HZvd0v2iEb0mO-Tn",
			"type": "arrow",
			"x": 5219.920686128527,
			"y": -2006.7543358554185,
			"width": 298.6669921875,
			"height": 64.00004069010402,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3Q",
			"roundness": {
				"type": 2
			},
			"seed": 1639294271,
			"version": 132,
			"versionNonce": 1949708511,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					298.6669921875,
					-64.00004069010402
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "yIVyOGlPXTWn1ZdYUWgvj",
				"focus": 0.4155281877186664,
				"gap": 1.672868939509982,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "iHW8EUqsAYmQ2NSUYN-TY",
				"focus": -0.7709501675198979,
				"gap": 1,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "aDCv-acCWlewaY2lVCiNf",
			"type": "arrow",
			"x": 5123.920930269152,
			"y": -2028.08775056896,
			"width": 245.333251953125,
			"height": 85.333251953125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3R",
			"roundness": {
				"type": 2
			},
			"seed": 1936500063,
			"version": 135,
			"versionNonce": 1171834143,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-245.333251953125,
					-85.333251953125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "yIVyOGlPXTWn1ZdYUWgvj",
				"focus": -0.05267181518106492,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "MjOxlEPtuFGqKuBAPbAtf",
				"focus": -0.40918418375853843,
				"gap": 1,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "TxccLFfO3aNKn1MeERijE",
			"type": "arrow",
			"x": 5401.256357905456,
			"y": -1846.7528661385609,
			"width": 229.33534625609536,
			"height": 149.33476236008687,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3S",
			"roundness": {
				"type": 2
			},
			"seed": 311337343,
			"version": 96,
			"versionNonce": 1239468351,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508930,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-229.33534625609536,
					-149.33476236008687
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "G3rsBYo1qxa9003uReIoR",
				"focus": -0.9179433307934212,
				"gap": 1.1356439340706928,
				"fixedPoint": null
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "YHd55HfPYeFzp63SoJSW0",
			"type": "arrow",
			"x": 5507.9207675087355,
			"y": -1878.754457925731,
			"width": 234.666748046875,
			"height": 69.33329264322902,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3T",
			"roundness": {
				"type": 2
			},
			"seed": 1348213151,
			"version": 127,
			"versionNonce": 1027655039,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					234.666748046875,
					-69.33329264322902
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "G3rsBYo1qxa9003uReIoR",
				"focus": 0.15903451148327907,
				"gap": 11.784778014989378,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "WCOi3Jo4s4XPnR8NPept6",
				"focus": -0.5404116341372351,
				"gap": 17.653314741538807,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "I0j-ziY7SyWew44M2QbbA",
			"type": "arrow",
			"x": 5827.9207675087355,
			"y": -2060.087669188752,
			"width": 95.999755859375,
			"height": 149.33329264322924,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3U",
			"roundness": {
				"type": 2
			},
			"seed": 1107660223,
			"version": 109,
			"versionNonce": 2038346175,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-95.999755859375,
					-149.33329264322924
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "WCOi3Jo4s4XPnR8NPept6",
				"focus": 0.7512021244013487,
				"gap": 2.3509087272881644,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "-5pg1LxJN16q5n7eaONBt",
				"focus": 0.10447405163665378,
				"gap": 16.450569888898052,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "qkSp1R8JrEy3RZKqncsIC",
			"type": "arrow",
			"x": 5747.9207675087355,
			"y": -2028.08775056896,
			"width": 303.99983723958303,
			"height": 357.3333740234375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3V",
			"roundness": {
				"type": 2
			},
			"seed": 44793311,
			"version": 162,
			"versionNonce": 1943965183,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-303.99983723958303,
					-357.3333740234375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "WCOi3Jo4s4XPnR8NPept6",
				"focus": -0.40954706635103144,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "k2xFp5l2jI8eSYLDo9S9H",
				"focus": -0.707338063636343,
				"gap": 3.455598546912192,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "S-DLsKJHpdspHFJZzEXA_",
			"type": "arrow",
			"x": 5475.920848888944,
			"y": -2102.7542951653145,
			"width": 213.33333333333394,
			"height": 112.0001220703125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3W",
			"roundness": {
				"type": 2
			},
			"seed": 1969121791,
			"version": 125,
			"versionNonce": 547641919,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-213.33333333333394,
					-112.0001220703125
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "iHW8EUqsAYmQ2NSUYN-TY",
				"focus": -0.4188274558427227,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "itk7MM0rbqszm3I2hXXM_",
				"focus": 0.2712549387179443,
				"gap": 5.931379565329038,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "HfCrGZJyGHJtgNJMkIhZA",
			"type": "arrow",
			"x": 5491.9210116493605,
			"y": -2150.7543765455225,
			"width": 58.6669921875,
			"height": 197.3333740234375,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3X",
			"roundness": {
				"type": 2
			},
			"seed": 1193202207,
			"version": 117,
			"versionNonce": 856954495,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-58.6669921875,
					-197.3333740234375
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "iHW8EUqsAYmQ2NSUYN-TY",
				"focus": -0.14168881364616964,
				"gap": 4.128136756027089,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "k2xFp5l2jI8eSYLDo9S9H",
				"focus": -0.5416857280624555,
				"gap": 15.607822111061253,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "WNWSUyF5Y1iin5GuvBV5m",
			"type": "arrow",
			"x": 4857.2542636024855,
			"y": -2316.0876284986475,
			"width": 48.00008138020803,
			"height": 160,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3Y",
			"roundness": {
				"type": 2
			},
			"seed": 819803711,
			"version": 118,
			"versionNonce": 1567736511,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-48.00008138020803,
					160
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "S3ejaZiJAQR1svjaVVzKy",
				"focus": 0.9540217633617681,
				"gap": 7.3751908398352555,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "MjOxlEPtuFGqKuBAPbAtf",
				"focus": -0.7235576372840568,
				"gap": 6.233748929551794,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "VCy8mhzBLEeam9dDNKBQs",
			"type": "arrow",
			"x": 4947.9207675087355,
			"y": -2326.7543358554185,
			"width": 389.33349609375,
			"height": 64.00004069010402,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3Z",
			"roundness": {
				"type": 2
			},
			"seed": 2038044255,
			"version": 156,
			"versionNonce": 285302527,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508931,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					389.33349609375,
					-64.00004069010402
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "S3ejaZiJAQR1svjaVVzKy",
				"focus": 0.2210282369883127,
				"gap": 1,
				"fixedPoint": null
			},
			"endBinding": {
				"elementId": "k2xFp5l2jI8eSYLDo9S9H",
				"focus": 0.10413008790512335,
				"gap": 3.704892734256269,
				"fixedPoint": null
			},
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "RUXBzKWW",
			"type": "text",
			"x": 3315.9208488889435,
			"y": -2305.4211245923975,
			"width": 1111.463623046875,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3a",
			"roundness": null,
			"seed": 935719551,
			"version": 160,
			"versionNonce": 1630780209,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"text": "Construct another graph and compute the new Laplacian matrix",
			"rawText": "Construct another graph and compute the new Laplacian matrix",
			"fontSize": 36,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Construct another graph and compute the new Laplacian matrix",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "yLCs6rYd",
			"type": "text",
			"x": 846.5873527951944,
			"y": -1500.0874657382287,
			"width": 1197.34375,
			"height": 180,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3b",
			"roundness": null,
			"seed": 1417759391,
			"version": 316,
			"versionNonce": 777465105,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"text": "Suppose that originally we have a data matrix A of dimension q x N,\nand a training data matrix q x M A^, we concatenate them and have\na new data matrix (M + N) x (M + N) A*\n",
			"rawText": "Suppose that originally we have a data matrix A of dimension q x N,\nand a training data matrix q x M A^, we concatenate them and have\na new data matrix (M + N) x (M + N) A*\n",
			"fontSize": 36,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Suppose that originally we have a data matrix A of dimension q x N,\nand a training data matrix q x M A^, we concatenate them and have\na new data matrix (M + N) x (M + N) A*\n",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "0ABQjWG6U2CdEQpxcloaF",
			"type": "freedraw",
			"x": 4765.478329952603,
			"y": -1394.8310180412213,
			"width": 15.015886904893515,
			"height": 142.6517848173477,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3c",
			"roundness": null,
			"seed": 1281138367,
			"version": 306,
			"versionNonce": 1307665137,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.630975489769727
				],
				[
					0,
					9.385054618600263
				],
				[
					0,
					15.01595850663183
				],
				[
					0,
					18.770037635462526
				],
				[
					0,
					22.52397356081691
				],
				[
					-1.8769679626771898,
					30.031988615001822
				],
				[
					-1.8769679626771898,
					35.66303570650955
				],
				[
					-3.7539359253543796,
					39.41697163186393
				],
				[
					-3.7539359253543796,
					45.04801872337181
				],
				[
					-3.7539359253543796,
					48.80195464872619
				],
				[
					-3.7539359253543796,
					52.555890574080564
				],
				[
					-5.63090388803157,
					56.309969702911104
				],
				[
					-5.63090388803157,
					60.06390562826549
				],
				[
					-5.63090388803157,
					63.81798475709602
				],
				[
					-7.508015054184755,
					67.5719206824504
				],
				[
					-7.508015054184755,
					69.44888864512758
				],
				[
					-7.508015054184755,
					73.20296777395828
				],
				[
					-7.508015054184755,
					75.07993573663548
				],
				[
					-7.508015054184755,
					76.95690369931266
				],
				[
					-7.508015054184755,
					80.71083962466705
				],
				[
					-7.508015054184755,
					82.58795079082039
				],
				[
					-7.508015054184755,
					86.34188671617477
				],
				[
					-7.508015054184755,
					88.21885467885195
				],
				[
					-9.384983016861945,
					91.9729338076825
				],
				[
					-9.384983016861945,
					93.84990177035968
				],
				[
					-9.384983016861945,
					95.72686973303686
				],
				[
					-11.261950979539135,
					97.60383769571406
				],
				[
					-11.261950979539135,
					101.35791682454476
				],
				[
					-11.261950979539135,
					105.11185274989913
				],
				[
					-11.261950979539135,
					106.98882071257633
				],
				[
					-11.261950979539135,
					108.86578867525353
				],
				[
					-11.261950979539135,
					110.74289984140687
				],
				[
					-11.261950979539135,
					112.61986780408404
				],
				[
					-11.261950979539135,
					114.49683576676124
				],
				[
					-13.138918942216323,
					114.49683576676124
				],
				[
					-13.138918942216323,
					116.37380372943845
				],
				[
					-13.138918942216323,
					118.2507716921156
				],
				[
					-13.138918942216323,
					123.88181878362333
				],
				[
					-13.138918942216323,
					127.63575470897774
				],
				[
					-13.138918942216323,
					129.5128658751312
				],
				[
					-13.138918942216323,
					133.2668018004856
				],
				[
					-13.138918942216323,
					137.02073772584
				],
				[
					-15.015886904893515,
					138.89784889199333
				],
				[
					-15.015886904893515,
					140.77481685467052
				],
				[
					-15.015886904893515,
					142.6517848173477
				],
				[
					-15.015886904893515,
					142.6517848173477
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "HbjBCmJvgm-fUaC1CiH4I",
			"type": "freedraw",
			"x": 4750.46244304771,
			"y": -1250.3022652611967,
			"width": 75.07986413489748,
			"height": 7.5080150541849155,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3d",
			"roundness": null,
			"seed": 838364895,
			"version": 287,
			"versionNonce": 1284103377,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.753935925354379,
					1.8769679626771898
				],
				[
					5.630903888031569,
					1.8769679626771898
				],
				[
					7.507871850708758,
					3.7540791288305355
				],
				[
					13.138918942216323,
					3.7540791288305355
				],
				[
					16.892854867570705,
					3.7540791288305355
				],
				[
					24.400869921756097,
					5.631047091507726
				],
				[
					28.15494905058647,
					5.631047091507726
				],
				[
					31.908884975940857,
					5.631047091507726
				],
				[
					35.662820901295234,
					5.631047091507726
				],
				[
					39.41690003012561,
					5.631047091507726
				],
				[
					41.293867992802795,
					5.631047091507726
				],
				[
					43.17083595547999,
					5.631047091507726
				],
				[
					45.04780391815717,
					5.631047091507726
				],
				[
					46.924915084310996,
					5.631047091507726
				],
				[
					48.801883046988195,
					5.631047091507726
				],
				[
					50.67885100966538,
					5.631047091507726
				],
				[
					52.555818972342564,
					7.5080150541849155
				],
				[
					54.43278693501977,
					7.5080150541849155
				],
				[
					60.063834026527324,
					7.5080150541849155
				],
				[
					61.940801989204516,
					7.5080150541849155
				],
				[
					63.817769951881715,
					7.5080150541849155
				],
				[
					67.57184908071208,
					7.5080150541849155
				],
				[
					69.44881704338927,
					7.5080150541849155
				],
				[
					71.32578500606647,
					7.5080150541849155
				],
				[
					73.20275296874364,
					7.5080150541849155
				],
				[
					75.07986413489748,
					7.5080150541849155
				],
				[
					75.07986413489748,
					7.5080150541849155
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "iHuqB5_kZj7VKamwSX_O4",
			"type": "freedraw",
			"x": 4906.253075205535,
			"y": -1289.719165291323,
			"width": 39.41690003012624,
			"height": 9.384983016862105,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3e",
			"roundness": null,
			"seed": 1877293823,
			"version": 281,
			"versionNonce": 968366769,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.8769679626771896
				],
				[
					1.8769679626771893,
					-1.8769679626771896
				],
				[
					5.631047091508204,
					-3.753935925354379
				],
				[
					7.508015054185393,
					-3.753935925354379
				],
				[
					11.26195097953977,
					-3.753935925354379
				],
				[
					15.016030108370146,
					-3.753935925354379
				],
				[
					16.892998071047337,
					-3.753935925354379
				],
				[
					20.64693399640171,
					-3.753935925354379
				],
				[
					22.5240451625549,
					-3.753935925354379
				],
				[
					24.40101312523209,
					-3.753935925354379
				],
				[
					30.031917013263655,
					-3.753935925354379
				],
				[
					31.90902817941748,
					-3.753935925354379
				],
				[
					33.785996142094675,
					-3.753935925354379
				],
				[
					35.66296410477186,
					-3.753935925354379
				],
				[
					37.53993206744905,
					-3.753935925354379
				],
				[
					39.41690003012624,
					-3.753935925354379
				],
				[
					39.41690003012624,
					-1.8769679626771896
				],
				[
					37.53993206744905,
					0
				],
				[
					35.66296410477186,
					1.8769679626771896
				],
				[
					33.785996142094675,
					3.753935925354379
				],
				[
					31.90902817941748,
					5.6310470915077255
				],
				[
					31.90902817941748,
					5.6310470915077255
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "-j5SkLDQqlIrhuU1EMVOJ",
			"type": "freedraw",
			"x": 4900.622171317505,
			"y": -1263.4411842034137,
			"width": 65.69488111803552,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3f",
			"roundness": null,
			"seed": 1252229919,
			"version": 274,
			"versionNonce": 1176738961,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.753935925354379,
					0
				],
				[
					9.384983016862584,
					0
				],
				[
					18.769966033724526,
					0
				],
				[
					26.277837884433286,
					0
				],
				[
					33.785852938618035,
					0
				],
				[
					41.293867992803435,
					0
				],
				[
					48.80188304698819,
					0
				],
				[
					52.55581897234256,
					0
				],
				[
					58.186866063850125,
					0
				],
				[
					60.06383402652732,
					0
				],
				[
					61.9408019892045,
					0
				],
				[
					63.81776995188171,
					0
				],
				[
					65.69488111803552,
					0
				],
				[
					65.69488111803552,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "RFqhgdJpsx5bnBpLPxW1B",
			"type": "freedraw",
			"x": 5043.273884533113,
			"y": -1409.8469765478535,
			"width": 80.71076802292905,
			"height": 16.89299807104718,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3g",
			"roundness": null,
			"seed": 581158719,
			"version": 284,
			"versionNonce": 562291313,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.8769679626771896,
					0
				],
				[
					-1.8769679626771896,
					-1.8769679626771898
				],
				[
					3.753935925354379,
					-3.754007527092378
				],
				[
					13.138918942216963,
					-5.630975489769568
				],
				[
					26.277981087909286,
					-9.384983016862105
				],
				[
					35.662964104771866,
					-11.261950979539295
				],
				[
					45.04794712163382,
					-11.261950979539295
				],
				[
					48.801883046988195,
					-13.138990543954645
				],
				[
					54.43278693501976,
					-13.138990543954645
				],
				[
					60.063834026527324,
					-13.138990543954645
				],
				[
					67.57199228418871,
					-13.138990543954645
				],
				[
					75.07986413489749,
					-13.138990543954645
				],
				[
					76.95697530105066,
					-13.138990543954645
				],
				[
					78.83380006025185,
					-13.138990543954645
				],
				[
					78.83380006025185,
					-11.261950979539295
				],
				[
					78.83380006025185,
					-7.507943452446758
				],
				[
					76.95697530105066,
					-3.754007527092378
				],
				[
					73.20275296874429,
					-1.8769679626771898
				],
				[
					71.3259282095431,
					0
				],
				[
					69.44881704338991,
					1.8770395644153481
				],
				[
					67.57199228418871,
					3.754007527092538
				],
				[
					63.8177699518817,
					3.754007527092538
				],
				[
					63.8177699518817,
					3.754007527092538
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "R7oFKLBiITYob1oK-J5k_",
			"type": "freedraw",
			"x": 5037.642837441606,
			"y": -1411.723944510531,
			"width": 114.49676416502308,
			"height": 251.5175734926011,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3h",
			"roundness": null,
			"seed": 1984333663,
			"version": 350,
			"versionNonce": 413166673,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					3.7540075270925377
				],
				[
					0,
					9.384983016862266
				],
				[
					0,
					15.015958506631833
				],
				[
					0,
					31.90888497594086
				],
				[
					0,
					43.17097915895647
				],
				[
					-1.8769679626771896,
					52.55596217581858
				],
				[
					-1.8769679626771896,
					63.817913155358035
				],
				[
					-3.753935925354379,
					73.20289617222014
				],
				[
					-3.753935925354379,
					80.71091122640506
				],
				[
					-5.630903888031569,
					91.97286220594451
				],
				[
					-7.508015054184755,
					99.48087726012942
				],
				[
					-9.384983016861945,
					108.86586027699153
				],
				[
					-11.261950979539135,
					114.49676416502311
				],
				[
					-13.138918942216321,
					122.00477921920817
				],
				[
					-13.138918942216321,
					127.63582631071591
				],
				[
					-13.138918942216321,
					131.38976223607028
				],
				[
					-13.138918942216321,
					135.14369816142465
				],
				[
					-15.015886904893515,
					138.89777729025516
				],
				[
					-15.015886904893515,
					142.6517132156096
				],
				[
					-15.015886904893515,
					146.40579234444027
				],
				[
					-15.015886904893515,
					150.15972826979464
				],
				[
					-15.015886904893515,
					153.91366419514904
				],
				[
					-15.015886904893515,
					159.54471128665676
				],
				[
					-16.89299807104734,
					163.29864721201113
				],
				[
					-16.89299807104734,
					167.05272634084167
				],
				[
					-16.89299807104734,
					170.80666226619604
				],
				[
					-16.89299807104734,
					172.68363022887326
				],
				[
					-16.89299807104734,
					174.56074139502675
				],
				[
					-16.89299807104734,
					176.4377093577039
				],
				[
					-16.89299807104734,
					178.31467732038115
				],
				[
					-16.89299807104734,
					180.19164528305834
				],
				[
					-16.89299807104734,
					182.0686132457355
				],
				[
					-16.89299807104734,
					183.94572441188885
				],
				[
					-16.89299807104734,
					185.82269237456606
				],
				[
					-16.89299807104734,
					189.57662829992043
				],
				[
					-16.89299807104734,
					193.33070742875094
				],
				[
					-16.89299807104734,
					198.96161131678252
				],
				[
					-16.89299807104734,
					202.7156904456132
				],
				[
					-16.89299807104734,
					206.46962637096763
				],
				[
					-16.89299807104734,
					212.1006734624753
				],
				[
					-16.89299807104734,
					213.97764142515254
				],
				[
					-16.89299807104734,
					215.8546093878297
				],
				[
					-16.89299807104734,
					217.73157735050688
				],
				[
					-16.89299807104734,
					219.60854531318412
				],
				[
					-16.89299807104734,
					221.48565647933745
				],
				[
					-16.89299807104734,
					225.2395924046918
				],
				[
					-16.89299807104734,
					227.11656036736903
				],
				[
					-16.89299807104734,
					228.99352833004622
				],
				[
					-16.89299807104734,
					230.87063949619971
				],
				[
					-16.89299807104734,
					232.7476074588769
				],
				[
					-16.89299807104734,
					234.62457542155408
				],
				[
					-15.015886904893515,
					234.62457542155408
				],
				[
					-15.015886904893515,
					238.37851134690848
				],
				[
					-15.015886904893515,
					240.2556225130618
				],
				[
					-15.015886904893515,
					244.00955843841618
				],
				[
					-15.015886904893515,
					245.8865264010934
				],
				[
					-15.015886904893515,
					247.76349436377058
				],
				[
					-15.015886904893515,
					249.64060552992396
				],
				[
					-11.261950979539135,
					249.64060552992396
				],
				[
					-9.384983016861945,
					249.64060552992396
				],
				[
					-5.630903888031569,
					249.64060552992396
				],
				[
					0,
					249.64060552992396
				],
				[
					5.631047091507565,
					247.76349436377058
				],
				[
					9.384983016861945,
					247.76349436377058
				],
				[
					13.139062145692963,
					247.76349436377058
				],
				[
					16.89299807104734,
					247.76349436377058
				],
				[
					18.76996603372453,
					247.76349436377058
				],
				[
					20.646933996401717,
					247.76349436377058
				],
				[
					22.524045162554902,
					247.76349436377058
				],
				[
					26.277981087909286,
					247.76349436377058
				],
				[
					28.154949050586474,
					247.76349436377058
				],
				[
					35.66296410477123,
					249.64060552992396
				],
				[
					41.294011196279435,
					249.64060552992396
				],
				[
					46.924915084310996,
					249.64060552992396
				],
				[
					52.55596217581857,
					249.64060552992396
				],
				[
					58.187009267326125,
					249.64060552992396
				],
				[
					65.69488111803489,
					249.64060552992396
				],
				[
					71.3259282095431,
					249.64060552992396
				],
				[
					75.07986413489748,
					249.64060552992396
				],
				[
					80.71091122640505,
					249.64060552992396
				],
				[
					84.46484715175943,
					249.64060552992396
				],
				[
					84.46484715175943,
					251.5175734926011
				],
				[
					86.3419583179126,
					251.5175734926011
				],
				[
					88.21878307711378,
					251.5175734926011
				],
				[
					90.09589424326698,
					251.5175734926011
				],
				[
					91.97300540942081,
					251.5175734926011
				],
				[
					93.84983016862138,
					251.5175734926011
				],
				[
					95.72694133477519,
					251.5175734926011
				],
				[
					97.60376609397574,
					251.5175734926011
				],
				[
					97.60376609397574,
					251.5175734926011
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "1C-aKarGOSztYTq8CFvxf",
			"type": "freedraw",
			"x": 5180.294693860692,
			"y": -1456.7718916321642,
			"width": 50.67885100966539,
			"height": 99.48087726012926,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3i",
			"roundness": null,
			"seed": 601637759,
			"version": 303,
			"versionNonce": 1934670385,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8770395644151878
				],
				[
					0,
					3.754007527092378
				],
				[
					0,
					5.630975489769568
				],
				[
					0,
					7.508015054184916
				],
				[
					0,
					11.262022581277453
				],
				[
					0,
					13.138990543954645
				],
				[
					0,
					18.76996603372421
				],
				[
					0,
					22.52397356081675
				],
				[
					0,
					28.154949050586477
				],
				[
					0,
					30.031988615001662
				],
				[
					0,
					35.66296410477139
				],
				[
					0,
					39.41697163186394
				],
				[
					0,
					45.0479471216335
				],
				[
					0,
					48.80195464872604
				],
				[
					0,
					54.432930138495756
				],
				[
					0,
					58.18693766558814
				],
				[
					0,
					61.94087359094252
				],
				[
					0,
					63.81791315535787
				],
				[
					0,
					67.57184908071224
				],
				[
					0,
					71.32592820954278
				],
				[
					0,
					73.20289617221998
				],
				[
					0,
					76.95683209757435
				],
				[
					0,
					78.83394326372787
				],
				[
					0,
					80.71091122640505
				],
				[
					0,
					82.58787918908223
				],
				[
					0,
					84.46484715175944
				],
				[
					0,
					86.34181511443661
				],
				[
					0,
					88.21892628058997
				],
				[
					1.8768247592011937,
					88.21892628058997
				],
				[
					5.631047091508205,
					90.09589424326715
				],
				[
					9.384983016862586,
					90.09589424326715
				],
				[
					15.01603010837015,
					91.97286220594435
				],
				[
					20.64679079292572,
					91.97286220594435
				],
				[
					24.401013125232097,
					93.84983016862154
				],
				[
					30.03177380978767,
					95.72679813129872
				],
				[
					31.908884975940854,
					95.72679813129872
				],
				[
					35.662820901295234,
					95.72679813129872
				],
				[
					39.41675682664961,
					95.72679813129872
				],
				[
					45.04780391815782,
					97.60390929745208
				],
				[
					46.924915084310996,
					99.48087726012926
				],
				[
					48.80173984351219,
					99.48087726012926
				],
				[
					50.67885100966539,
					99.48087726012926
				],
				[
					50.67885100966539,
					99.48087726012926
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "j5B0eaTZklYTX_XAjlZkg",
			"type": "freedraw",
			"x": 5255.37455799559,
			"y": -1400.4619935309906,
			"width": 28.154949050586474,
			"height": 61.94094519268067,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3j",
			"roundness": null,
			"seed": 1806007199,
			"version": 293,
			"versionNonce": 310135825,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.8771111661531859,
					3.7540075270923774
				],
				[
					-3.7539359253543796,
					7.5080150541849155
				],
				[
					-3.7539359253543796,
					11.261950979539293
				],
				[
					-5.631047091507566,
					16.89299807104702
				],
				[
					-5.631047091507566,
					20.646933996401398
				],
				[
					-5.631047091507566,
					26.277981087909286
				],
				[
					-5.631047091507566,
					30.03191701326366
				],
				[
					-7.5081582576613926,
					33.7859961420942
				],
				[
					-7.5081582576613926,
					37.53993206744858
				],
				[
					-7.5081582576613926,
					39.41690003012577
				],
				[
					-7.5081582576613926,
					41.294011196279115
				],
				[
					-7.5081582576613926,
					43.1709791589563
				],
				[
					-7.5081582576613926,
					45.04794712163349
				],
				[
					-7.5081582576613926,
					46.92491508431069
				],
				[
					-7.5081582576613926,
					48.80188304698787
				],
				[
					-7.5081582576613926,
					50.67899421314137
				],
				[
					-7.5081582576613926,
					52.55596217581857
				],
				[
					-7.5081582576613926,
					54.43293013849575
				],
				[
					-7.5081582576613926,
					56.30989810117295
				],
				[
					-7.5081582576613926,
					58.18686606385014
				],
				[
					-5.631047091507566,
					60.06397723000349
				],
				[
					-3.7539359253543796,
					61.94094519268067
				],
				[
					-1.8771111661531859,
					61.94094519268067
				],
				[
					0,
					61.94094519268067
				],
				[
					1.876824759201194,
					61.94094519268067
				],
				[
					5.631047091507566,
					61.94094519268067
				],
				[
					9.384983016861945,
					61.94094519268067
				],
				[
					11.261807776063138,
					61.94094519268067
				],
				[
					15.016030108370153,
					60.06397723000349
				],
				[
					16.892854867570705,
					60.06397723000349
				],
				[
					18.769966033724533,
					60.06397723000349
				],
				[
					20.64679079292508,
					58.18686606385014
				],
				[
					20.64679079292508,
					58.18686606385014
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "xBXNBdAEZAfMvBkUFuXMO",
			"type": "freedraw",
			"x": 5302.2994730799,
			"y": -1402.3389614936682,
			"width": 31.908884975940854,
			"height": 67.5719206824504,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3k",
			"roundness": null,
			"seed": 835891135,
			"version": 295,
			"versionNonce": 1310368241,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.8771111661538258,
					-1.8770395644153477
				],
				[
					-1.8771111661538258,
					0
				],
				[
					-1.8771111661538258,
					3.754007527092377
				],
				[
					-1.8771111661538258,
					7.5079434524467565
				],
				[
					-1.8771111661538258,
					9.384983016862103
				],
				[
					-1.8771111661538258,
					13.138918942216483
				],
				[
					-1.8771111661538258,
					16.892998071047018
				],
				[
					-1.8771111661538258,
					22.523901959078586
				],
				[
					-1.8771111661538258,
					30.031917013263655
				],
				[
					-1.8771111661538258,
					33.78599614209419
				],
				[
					-1.8771111661538258,
					37.539932067448575
				],
				[
					-1.8771111661538258,
					39.41690003012576
				],
				[
					-3.753935925354379,
					43.17097915895629
				],
				[
					-3.753935925354379,
					46.92491508431068
				],
				[
					-3.753935925354379,
					48.80188304698786
				],
				[
					-3.753935925354379,
					52.555962175818564
				],
				[
					-3.753935925354379,
					54.43293013849574
				],
				[
					-3.753935925354379,
					56.30989810117294
				],
				[
					-3.753935925354379,
					58.18686606385013
				],
				[
					-3.753935925354379,
					60.06383402652731
				],
				[
					-3.753935925354379,
					61.940945192680665
				],
				[
					-3.753935925354379,
					63.81791315535786
				],
				[
					-1.8771111661538258,
					65.69488111803506
				],
				[
					1.8768247592005531,
					65.69488111803506
				],
				[
					5.631047091507564,
					65.69488111803506
				],
				[
					7.507871850708758,
					65.69488111803506
				],
				[
					11.261807776063137,
					65.69488111803506
				],
				[
					16.892854867570698,
					65.69488111803506
				],
				[
					20.64679079292508,
					65.69488111803506
				],
				[
					22.523901959078266,
					65.69488111803506
				],
				[
					26.277837884432643,
					65.69488111803506
				],
				[
					26.277837884432643,
					63.81791315535786
				],
				[
					28.15494905058647,
					63.81791315535786
				],
				[
					28.15494905058647,
					63.81791315535786
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "PfneiV-cKF_27RwkjBVkb",
			"type": "freedraw",
			"x": 5461.844184366557,
			"y": -1479.2958651929816,
			"width": 60.06383402652732,
			"height": 108.86578867525353,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3l",
			"roundness": null,
			"seed": 8675295,
			"version": 292,
			"versionNonce": 322124753,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.6310470915078845
				],
				[
					0,
					9.384983016862265
				],
				[
					0,
					15.016030108369993
				],
				[
					0,
					18.76996603372437
				],
				[
					-1.8771111661531852,
					24.401013125232097
				],
				[
					-1.8771111661531852,
					31.90895657767901
				],
				[
					-1.8771111661531852,
					35.66296410477155
				],
				[
					-3.753935925354379,
					43.17097915895646
				],
				[
					-3.753935925354379,
					46.92491508431084
				],
				[
					-3.753935925354379,
					52.55596217581857
				],
				[
					-5.631047091507564,
					56.30989810117295
				],
				[
					-5.631047091507564,
					61.940945192680836
				],
				[
					-5.631047091507564,
					65.69488111803521
				],
				[
					-5.631047091507564,
					73.20289617222012
				],
				[
					-5.631047091507564,
					76.95690369931266
				],
				[
					-5.631047091507564,
					80.71091122640505
				],
				[
					-7.508158257660749,
					84.46484715175943
				],
				[
					-7.508158257660749,
					88.21885467885195
				],
				[
					-9.384983016861943,
					91.9729338076825
				],
				[
					-9.384983016861943,
					93.84990177035968
				],
				[
					-9.384983016861943,
					97.60383769571406
				],
				[
					-9.384983016861943,
					99.48080565839125
				],
				[
					-9.384983016861943,
					101.35791682454476
				],
				[
					-9.384983016861943,
					103.23488478722196
				],
				[
					-9.384983016861943,
					105.11185274989913
				],
				[
					-7.508158257660749,
					105.11185274989913
				],
				[
					-5.631047091507564,
					105.11185274989913
				],
				[
					-3.753935925354379,
					105.11185274989913
				],
				[
					0,
					105.11185274989913
				],
				[
					1.8768247592011933,
					105.11185274989913
				],
				[
					5.631047091508205,
					105.11185274989913
				],
				[
					7.507871850708758,
					105.11185274989913
				],
				[
					9.384983016862584,
					105.11185274989913
				],
				[
					11.261807776063137,
					105.11185274989913
				],
				[
					13.138918942216963,
					105.11185274989913
				],
				[
					15.016030108370147,
					105.11185274989913
				],
				[
					16.892854867571344,
					105.11185274989913
				],
				[
					18.769966033724526,
					106.98882071257633
				],
				[
					20.64679079292572,
					106.98882071257633
				],
				[
					22.523901959078906,
					106.98882071257633
				],
				[
					24.40101312523209,
					106.98882071257633
				],
				[
					28.154949050586467,
					106.98882071257633
				],
				[
					31.908884975940854,
					108.86578867525353
				],
				[
					33.785996142094675,
					108.86578867525353
				],
				[
					37.53993206744905,
					108.86578867525353
				],
				[
					39.4167568266496,
					108.86578867525353
				],
				[
					43.17097915895662,
					108.86578867525353
				],
				[
					45.04780391815781,
					108.86578867525353
				],
				[
					46.924915084310996,
					108.86578867525353
				],
				[
					48.80173984351219,
					108.86578867525353
				],
				[
					50.67885100966538,
					108.86578867525353
				],
				[
					50.67885100966538,
					108.86578867525353
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "VELopc0K4qAx25JV3uCup",
			"type": "freedraw",
			"x": 5540.6779844268085,
			"y": -1379.81505953459,
			"width": 39.41675682664961,
			"height": 46.92491508431084,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3m",
			"roundness": null,
			"seed": 1238043647,
			"version": 294,
			"versionNonce": 1105041841,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.877111166153506
				],
				[
					0,
					3.754079128830696
				],
				[
					0,
					5.6310470915078845
				],
				[
					0,
					7.508015054185075
				],
				[
					0,
					11.26209418301561
				],
				[
					0,
					13.139062145692801
				],
				[
					0,
					16.89299807104718
				],
				[
					-1.8771111661531854,
					20.647077199877714
				],
				[
					-1.8771111661531854,
					24.401013125232097
				],
				[
					-3.7539359253543787,
					26.277981087909286
				],
				[
					-3.7539359253543787,
					30.032060216739985
				],
				[
					-3.7539359253543787,
					31.909028179417167
				],
				[
					-3.7539359253543787,
					33.78599614209436
				],
				[
					-3.7539359253543787,
					35.66296410477155
				],
				[
					-3.7539359253543787,
					37.53993206744874
				],
				[
					-3.7539359253543787,
					39.41704323360209
				],
				[
					-3.7539359253543787,
					43.17097915895646
				],
				[
					-3.7539359253543787,
					45.047947121633655
				],
				[
					-3.7539359253543787,
					46.92491508431084
				],
				[
					-1.8771111661531854,
					46.92491508431084
				],
				[
					0,
					46.92491508431084
				],
				[
					3.7539359253543787,
					46.92491508431084
				],
				[
					5.631047091507565,
					46.92491508431084
				],
				[
					9.384983016861943,
					46.92491508431084
				],
				[
					13.138918942216321,
					46.92491508431084
				],
				[
					15.016030108370149,
					46.92491508431084
				],
				[
					16.8928548675707,
					46.92491508431084
				],
				[
					22.523901959078906,
					46.92491508431084
				],
				[
					26.277837884433282,
					45.047947121633655
				],
				[
					30.03206021673966,
					43.17097915895646
				],
				[
					31.90888497594085,
					43.17097915895646
				],
				[
					33.785996142094035,
					41.29401119627927
				],
				[
					35.66282090129523,
					41.29401119627927
				],
				[
					35.66282090129523,
					41.29401119627927
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "S-xfd9gG-R8PjDeAWWip1",
			"type": "freedraw",
			"x": 5580.09502766041,
			"y": -1377.9379483684365,
			"width": 48.801739843510916,
			"height": 50.67885100966506,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3n",
			"roundness": null,
			"seed": 1772565535,
			"version": 322,
			"versionNonce": 1262566289,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.753935925354379
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					7.507871850708758
				],
				[
					0,
					11.261950979539293
				],
				[
					0,
					15.015886904893673
				],
				[
					0,
					16.892854867570865
				],
				[
					0,
					20.646933996401398
				],
				[
					1.8768247592005536,
					24.400869921755778
				],
				[
					1.8768247592005536,
					28.154949050586474
				],
				[
					1.8768247592005536,
					30.03191701326366
				],
				[
					3.753935925354379,
					31.908884975940854
				],
				[
					3.753935925354379,
					33.78585293861804
				],
				[
					5.630760684554933,
					35.662820901295234
				],
				[
					5.630760684554933,
					37.53993206744858
				],
				[
					7.507871850708758,
					41.29386799280295
				],
				[
					9.384983016861304,
					41.29386799280295
				],
				[
					11.261807776063138,
					43.17083595548015
				],
				[
					13.138918942215682,
					45.047803918157335
				],
				[
					15.015743701417517,
					46.92491508431069
				],
				[
					16.892854867570062,
					46.92491508431069
				],
				[
					18.76996603372389,
					46.92491508431069
				],
				[
					18.76996603372389,
					48.80188304698787
				],
				[
					20.646790792924442,
					48.80188304698787
				],
				[
					22.52390195907827,
					48.80188304698787
				],
				[
					24.400726718278822,
					48.80188304698787
				],
				[
					24.400726718278822,
					50.67885100966506
				],
				[
					26.277837884432643,
					50.67885100966506
				],
				[
					28.154949050586474,
					50.67885100966506
				],
				[
					30.03177380978703,
					50.67885100966506
				],
				[
					31.908884975940854,
					50.67885100966506
				],
				[
					33.7857097351414,
					50.67885100966506
				],
				[
					35.662820901295234,
					48.80188304698787
				],
				[
					37.53993206744778,
					48.80188304698787
				],
				[
					39.41675682664961,
					46.92491508431069
				],
				[
					41.29386799280215,
					46.92491508431069
				],
				[
					41.29386799280215,
					45.047803918157335
				],
				[
					43.170692752003994,
					43.17083595548015
				],
				[
					43.170692752003994,
					41.29386799280295
				],
				[
					45.04780391815654,
					39.41690003012577
				],
				[
					46.92491508431036,
					37.53993206744858
				],
				[
					46.92491508431036,
					35.662820901295234
				],
				[
					46.92491508431036,
					33.78585293861804
				],
				[
					46.92491508431036,
					31.908884975940854
				],
				[
					46.92491508431036,
					30.03191701326366
				],
				[
					46.92491508431036,
					28.154949050586474
				],
				[
					46.92491508431036,
					26.27783788443297
				],
				[
					46.92491508431036,
					24.400869921755778
				],
				[
					46.92491508431036,
					22.523901959078586
				],
				[
					46.92491508431036,
					20.646933996401398
				],
				[
					46.92491508431036,
					18.76996603372421
				],
				[
					46.92491508431036,
					16.892854867570865
				],
				[
					46.92491508431036,
					15.015886904893673
				],
				[
					46.92491508431036,
					13.138918942216485
				],
				[
					46.92491508431036,
					11.261950979539293
				],
				[
					46.92491508431036,
					9.384983016862105
				],
				[
					46.92491508431036,
					7.507871850708758
				],
				[
					48.801739843510916,
					5.630903888031569
				],
				[
					48.801739843510916,
					3.753935925354379
				],
				[
					48.801739843510916,
					1.8769679626771896
				],
				[
					48.801739843510916,
					0
				],
				[
					48.801739843510916,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "9nc3DnMFZSfZ6ooFRksb3",
			"type": "freedraw",
			"x": 5187.802565711401,
			"y": -1282.2111502371376,
			"width": 61.94094519268116,
			"height": 112.6197962023459,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3o",
			"roundness": null,
			"seed": 1745442879,
			"version": 312,
			"versionNonce": 261464433,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.8771111661538267,
					0
				],
				[
					1.8771111661538267,
					3.753935925354379
				],
				[
					1.8771111661538267,
					9.384983016862105
				],
				[
					1.8771111661538267,
					16.89299807104718
				],
				[
					1.8771111661538267,
					20.646933996401557
				],
				[
					1.8771111661538267,
					24.40086992175594
				],
				[
					1.8771111661538267,
					30.03191701326366
				],
				[
					1.8771111661538267,
					33.78585293861804
				],
				[
					1.8771111661538267,
					39.41690003012577
				],
				[
					1.8771111661538267,
					43.17083595548015
				],
				[
					1.8771111661538267,
					48.80188304698803
				],
				[
					1.8771111661538267,
					54.43293013849575
				],
				[
					1.8771111661538267,
					58.18686606385014
				],
				[
					1.8771111661538267,
					61.94080198920451
				],
				[
					1.8771111661538267,
					67.57184908071224
				],
				[
					1.8771111661538267,
					71.32578500606662
				],
				[
					1.8771111661538267,
					76.9568320975745
				],
				[
					3.7539359253543805,
					80.71076802292889
				],
				[
					3.7539359253543805,
					86.34181511443661
				],
				[
					3.7539359253543805,
					88.21878307711378
				],
				[
					3.7539359253543805,
					90.095751039791
				],
				[
					3.7539359253543805,
					91.97286220594434
				],
				[
					3.7539359253543805,
					93.84983016862152
				],
				[
					3.7539359253543805,
					97.6037660939759
				],
				[
					3.7539359253543805,
					99.48073405665309
				],
				[
					5.631047091508206,
					101.35784522280659
				],
				[
					5.631047091508206,
					103.2348131854838
				],
				[
					5.631047091508206,
					105.11178114816099
				],
				[
					5.631047091508206,
					106.98874911083816
				],
				[
					5.631047091508206,
					108.86571707351536
				],
				[
					7.508158257661393,
					108.86571707351536
				],
				[
					7.508158257661393,
					110.74282823966873
				],
				[
					7.508158257661393,
					112.6197962023459
				],
				[
					9.384983016862588,
					112.6197962023459
				],
				[
					11.262094183015773,
					112.6197962023459
				],
				[
					13.138918942216966,
					112.6197962023459
				],
				[
					15.016030108370154,
					112.6197962023459
				],
				[
					16.893141274523337,
					110.74282823966873
				],
				[
					20.647077199877717,
					110.74282823966873
				],
				[
					24.4010131252321,
					110.74282823966873
				],
				[
					31.90888497594086,
					110.74282823966873
				],
				[
					37.539932067449065,
					108.86571707351536
				],
				[
					41.29386799280345,
					108.86571707351536
				],
				[
					46.92491508431101,
					106.98874911083816
				],
				[
					50.678851009665394,
					106.98874911083816
				],
				[
					52.555962175818586,
					105.11178114816099
				],
				[
					54.43307334197241,
					105.11178114816099
				],
				[
					56.309898101172955,
					105.11178114816099
				],
				[
					58.18700926732679,
					105.11178114816099
				],
				[
					60.063834026527346,
					105.11178114816099
				],
				[
					61.94094519268116,
					105.11178114816099
				],
				[
					61.94094519268116,
					105.11178114816099
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "sqyMBHX83gSLaxNK3K24Z",
			"type": "freedraw",
			"x": 5268.5134769378055,
			"y": -1186.4843521058388,
			"width": 30.0320602167403,
			"height": 31.908884975940854,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3p",
			"roundness": null,
			"seed": 2060580959,
			"version": 297,
			"versionNonce": 2082622289,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.753935925354379
				],
				[
					1.8771111661538262,
					3.753935925354379
				],
				[
					1.8771111661538262,
					7.508015054185075
				],
				[
					1.8771111661538262,
					11.261950979539455
				],
				[
					1.8771111661538262,
					13.138918942216643
				],
				[
					1.8771111661538262,
					16.89299807104718
				],
				[
					1.8771111661538262,
					20.646933996401557
				],
				[
					1.8771111661538262,
					22.523901959078746
				],
				[
					3.7539359253543796,
					22.523901959078746
				],
				[
					3.7539359253543796,
					24.401013125232097
				],
				[
					3.7539359253543796,
					26.277981087909286
				],
				[
					5.631047091508205,
					26.277981087909286
				],
				[
					7.507871850708759,
					28.154949050586474
				],
				[
					9.384983016862586,
					30.03191701326366
				],
				[
					11.26209418301577,
					30.03191701326366
				],
				[
					11.26209418301577,
					31.908884975940854
				],
				[
					13.138918942216964,
					31.908884975940854
				],
				[
					15.01603010837015,
					31.908884975940854
				],
				[
					16.892854867571344,
					31.908884975940854
				],
				[
					18.769966033724533,
					31.908884975940854
				],
				[
					20.647077199877717,
					31.908884975940854
				],
				[
					20.647077199877717,
					30.03191701326366
				],
				[
					22.52390195907891,
					28.154949050586474
				],
				[
					26.27783788443329,
					26.277981087909286
				],
				[
					26.27783788443329,
					24.401013125232097
				],
				[
					26.27783788443329,
					20.646933996401557
				],
				[
					28.154949050586477,
					18.76996603372437
				],
				[
					28.154949050586477,
					16.89299807104718
				],
				[
					28.154949050586477,
					15.016030108369993
				],
				[
					28.154949050586477,
					13.138918942216643
				],
				[
					30.0320602167403,
					9.384983016862265
				],
				[
					30.0320602167403,
					7.508015054185075
				],
				[
					30.0320602167403,
					5.6310470915078845
				],
				[
					30.0320602167403,
					3.753935925354379
				],
				[
					30.0320602167403,
					0
				],
				[
					30.0320602167403,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "Zpz_n1K7241su5Wu3bPKN",
			"type": "freedraw",
			"x": 5326.700486205133,
			"y": -1197.7463030853783,
			"width": 31.908884975940854,
			"height": 48.80188304698803,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3q",
			"roundness": null,
			"seed": 1204917375,
			"version": 290,
			"versionNonce": 1765718321,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.753935925354379
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					11.261950979539293
				],
				[
					0,
					15.015886904893673
				],
				[
					0,
					16.89299807104718
				],
				[
					0,
					20.646933996401557
				],
				[
					0,
					26.277981087909286
				],
				[
					0,
					31.908884975940854
				],
				[
					0,
					35.66296410477138
				],
				[
					0,
					39.41690003012577
				],
				[
					0,
					43.17083595548015
				],
				[
					0,
					45.047947121633655
				],
				[
					0,
					46.92491508431084
				],
				[
					0,
					48.80188304698803
				],
				[
					3.753935925354379,
					48.80188304698803
				],
				[
					5.630760684554933,
					48.80188304698803
				],
				[
					9.384983016861945,
					48.80188304698803
				],
				[
					13.138918942216321,
					48.80188304698803
				],
				[
					15.015743701417517,
					48.80188304698803
				],
				[
					16.8928548675707,
					48.80188304698803
				],
				[
					18.76996603372389,
					48.80188304698803
				],
				[
					20.64679079292508,
					48.80188304698803
				],
				[
					22.52390195907827,
					48.80188304698803
				],
				[
					24.40072671827946,
					48.80188304698803
				],
				[
					26.277837884432643,
					48.80188304698803
				],
				[
					28.154949050586474,
					48.80188304698803
				],
				[
					30.03177380978703,
					48.80188304698803
				],
				[
					31.908884975940854,
					48.80188304698803
				],
				[
					31.908884975940854,
					48.80188304698803
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "EgCgSCSOIDCfY8BQavu8L",
			"type": "freedraw",
			"x": 5469.352056217265,
			"y": -1267.195263332244,
			"width": 52.55596217581857,
			"height": 101.35784522280659,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3r",
			"roundness": null,
			"seed": 1724427423,
			"version": 296,
			"versionNonce": 944925457,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.877111166153506
				],
				[
					0,
					7.508015054185075
				],
				[
					0,
					13.139062145692801
				],
				[
					0,
					20.647077199877714
				],
				[
					0,
					28.154949050586474
				],
				[
					0,
					33.78599614209436
				],
				[
					0,
					41.29401119627927
				],
				[
					0,
					48.802026250464195
				],
				[
					0,
					56.30989810117295
				],
				[
					0,
					65.69488111803521
				],
				[
					0,
					71.32592820954294
				],
				[
					0,
					78.83394326372786
				],
				[
					0,
					82.58787918908222
				],
				[
					0,
					86.34195831791293
				],
				[
					0,
					88.21892628059011
				],
				[
					0,
					90.09589424326731
				],
				[
					0,
					91.9728622059445
				],
				[
					0,
					93.84983016862168
				],
				[
					0,
					95.72694133477503
				],
				[
					0,
					97.60390929745222
				],
				[
					0,
					99.48087726012942
				],
				[
					1.8771111661538258,
					99.48087726012942
				],
				[
					5.631047091508205,
					99.48087726012942
				],
				[
					11.262094183015769,
					99.48087726012942
				],
				[
					15.01603010837015,
					99.48087726012942
				],
				[
					20.647077199877714,
					99.48087726012942
				],
				[
					24.401013125232097,
					99.48087726012942
				],
				[
					28.154949050586474,
					99.48087726012942
				],
				[
					31.908884975940854,
					99.48087726012942
				],
				[
					37.53993206744906,
					101.35784522280659
				],
				[
					41.293867992803435,
					101.35784522280659
				],
				[
					43.17097915895662,
					101.35784522280659
				],
				[
					46.924915084310996,
					101.35784522280659
				],
				[
					50.67885100966539,
					101.35784522280659
				],
				[
					52.55596217581857,
					101.35784522280659
				],
				[
					52.55596217581857,
					101.35784522280659
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "v6q1P-zDiLqNtIKqdyVOh",
			"type": "freedraw",
			"x": 5540.6779844268085,
			"y": -1175.2224011262992,
			"width": 26.277837884433286,
			"height": 30.03191701326366,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3s",
			"roundness": null,
			"seed": 594002111,
			"version": 288,
			"versionNonce": 836034801,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.7540791288305346
				],
				[
					0,
					5.631047091507725
				],
				[
					0,
					9.384983016862103
				],
				[
					0,
					15.016030108369828
				],
				[
					0,
					16.892998071047018
				],
				[
					0,
					18.769966033724206
				],
				[
					0,
					20.646933996401398
				],
				[
					0,
					22.524045162554902
				],
				[
					0,
					24.40101312523209
				],
				[
					0,
					26.27798108790928
				],
				[
					0,
					28.154949050586467
				],
				[
					1.8771111661531852,
					28.154949050586467
				],
				[
					1.8771111661531852,
					30.03191701326366
				],
				[
					5.631047091507564,
					30.03191701326366
				],
				[
					7.507871850708758,
					30.03191701326366
				],
				[
					9.384983016861943,
					30.03191701326366
				],
				[
					11.262094183015769,
					30.03191701326366
				],
				[
					13.138918942216321,
					28.154949050586467
				],
				[
					16.8928548675707,
					26.27798108790928
				],
				[
					16.8928548675707,
					24.40101312523209
				],
				[
					20.647077199877714,
					22.524045162554902
				],
				[
					20.647077199877714,
					20.646933996401398
				],
				[
					22.523901959078906,
					20.646933996401398
				],
				[
					22.523901959078906,
					18.769966033724206
				],
				[
					24.40101312523209,
					16.892998071047018
				],
				[
					26.277837884433286,
					16.892998071047018
				],
				[
					26.277837884433286,
					15.016030108369828
				],
				[
					26.277837884433286,
					15.016030108369828
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "780t-yd3zUUz0VIYL_-qY",
			"type": "freedraw",
			"x": 5563.201886385887,
			"y": -1180.853305014331,
			"width": 0,
			"height": 33.78585293861804,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3t",
			"roundness": null,
			"seed": 2135904479,
			"version": 279,
			"versionNonce": 592288465,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.753935925354379
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					7.507871850708758
				],
				[
					0,
					9.384983016862105
				],
				[
					0,
					11.261950979539293
				],
				[
					0,
					13.138918942216485
				],
				[
					0,
					15.015886904893673
				],
				[
					0,
					16.892854867570865
				],
				[
					0,
					18.76996603372421
				],
				[
					0,
					20.646933996401398
				],
				[
					0,
					22.523901959078586
				],
				[
					0,
					24.400869921755778
				],
				[
					0,
					26.27783788443297
				],
				[
					0,
					28.154949050586474
				],
				[
					0,
					30.03191701326366
				],
				[
					0,
					31.908884975940854
				],
				[
					0,
					33.78585293861804
				],
				[
					0,
					33.78585293861804
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "pzit4gFH8z-vxRmyRi4kj",
			"type": "freedraw",
			"x": 5585.725788344966,
			"y": -1177.0993690889768,
			"width": 22.524188366031538,
			"height": 30.03191701326366,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3u",
			"roundness": null,
			"seed": 1947196671,
			"version": 294,
			"versionNonce": 1028921521,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.753935925354379
				],
				[
					0,
					5.631047091507725
				],
				[
					0,
					11.261950979539293
				],
				[
					0,
					13.138918942216481
				],
				[
					0,
					15.016030108369828
				],
				[
					0,
					18.769966033724206
				],
				[
					0,
					20.646933996401398
				],
				[
					0,
					24.40101312523209
				],
				[
					0,
					26.27798108790928
				],
				[
					0,
					28.154949050586467
				],
				[
					0,
					30.03191701326366
				],
				[
					1.8771111661538256,
					30.03191701326366
				],
				[
					3.754222332306371,
					30.03191701326366
				],
				[
					5.631047091508205,
					30.03191701326366
				],
				[
					7.5081582576607495,
					30.03191701326366
				],
				[
					9.384983016862584,
					28.154949050586467
				],
				[
					9.384983016862584,
					26.27798108790928
				],
				[
					11.26209418301513,
					26.27798108790928
				],
				[
					13.139205349168956,
					26.27798108790928
				],
				[
					15.016030108369508,
					24.40101312523209
				],
				[
					16.893141274523334,
					22.523901959078586
				],
				[
					18.769966033723886,
					22.523901959078586
				],
				[
					18.769966033723886,
					20.646933996401398
				],
				[
					20.647077199877714,
					18.769966033724206
				],
				[
					20.647077199877714,
					16.892998071047018
				],
				[
					22.524188366031538,
					16.892998071047018
				],
				[
					22.524188366031538,
					15.016030108369828
				],
				[
					22.524188366031538,
					13.138918942216481
				],
				[
					22.524188366031538,
					11.261950979539293
				],
				[
					22.524188366031538,
					9.384983016862103
				],
				[
					22.524188366031538,
					7.508015054184914
				],
				[
					22.524188366031538,
					5.631047091507725
				],
				[
					22.524188366031538,
					5.631047091507725
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "d3UvieOlzGTROpbIalN99",
			"type": "freedraw",
			"x": 5608.249976710997,
			"y": -1178.9763370516544,
			"width": 1.8771111661538258,
			"height": 39.41690003012577,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3v",
			"roundness": null,
			"seed": 1965679903,
			"version": 275,
			"versionNonce": 831511185,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.8769679626771896
				],
				[
					0,
					3.753935925354379
				],
				[
					0,
					7.508015054184914
				],
				[
					0,
					11.261950979539293
				],
				[
					0,
					13.138918942216481
				],
				[
					0,
					16.892998071047018
				],
				[
					0,
					20.646933996401398
				],
				[
					0,
					22.523901959078586
				],
				[
					-1.8771111661538258,
					26.27798108790928
				],
				[
					-1.8771111661538258,
					28.154949050586467
				],
				[
					-1.8771111661538258,
					31.908884975940854
				],
				[
					-1.8771111661538258,
					35.66296410477138
				],
				[
					-1.8771111661538258,
					37.539932067448575
				],
				[
					-1.8771111661538258,
					39.41690003012577
				],
				[
					-1.8771111661538258,
					39.41690003012577
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "DvoYc62qZF3Y3ygty_Kb8",
			"type": "freedraw",
			"x": 5672.067746662879,
			"y": -1447.3869086153022,
			"width": 84.46484715175943,
			"height": 292.81144148540403,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3w",
			"roundness": null,
			"seed": 839772479,
			"version": 375,
			"versionNonce": 280518769,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.8771111661525455,
					0
				],
				[
					5.631047091506924,
					0
				],
				[
					11.26209418301513,
					0
				],
				[
					18.76996603372389,
					0
				],
				[
					24.401013125232097,
					0
				],
				[
					30.03206021673902,
					0
				],
				[
					35.662820901295234,
					-1.8769679626771898
				],
				[
					41.29386799280215,
					-1.8769679626771898
				],
				[
					46.92491508431036,
					-1.8769679626771898
				],
				[
					50.67885100966475,
					-1.8769679626771898
				],
				[
					52.55596217581857,
					-1.8769679626771898
				],
				[
					54.432786935019124,
					-1.8769679626771898
				],
				[
					56.30989810117295,
					-1.8769679626771898
				],
				[
					58.18700926732549,
					-1.8769679626771898
				],
				[
					60.06383402652732,
					-1.8769679626771898
				],
				[
					61.94094519267988,
					-1.8769679626771898
				],
				[
					63.81776995188171,
					-1.8769679626771898
				],
				[
					63.81776995188171,
					0
				],
				[
					65.69488111803425,
					0
				],
				[
					67.57199228418808,
					1.8770395644153477
				],
				[
					69.44881704338863,
					1.8770395644153477
				],
				[
					69.44881704338863,
					3.7540075270925373
				],
				[
					69.44881704338863,
					5.630975489769726
				],
				[
					69.44881704338863,
					7.508015054184915
				],
				[
					71.32592820954245,
					15.015958506631831
				],
				[
					71.32592820954245,
					20.647005598139557
				],
				[
					71.32592820954245,
					26.277981087909286
				],
				[
					71.32592820954245,
					31.908956577679007
				],
				[
					71.32592820954245,
					37.539932067448575
				],
				[
					71.32592820954245,
					43.17090755721831
				],
				[
					71.32592820954245,
					50.678922611403216
				],
				[
					71.32592820954245,
					54.43293013849575
				],
				[
					73.20275296874301,
					61.94094519268068
				],
				[
					73.20275296874301,
					67.57184908071224
				],
				[
					73.20275296874301,
					75.07986413489732
				],
				[
					73.20275296874301,
					78.83394326372786
				],
				[
					75.07986413489684,
					86.34181511443661
				],
				[
					75.07986413489684,
					91.97286220594434
				],
				[
					75.07986413489684,
					95.72679813129871
				],
				[
					75.07986413489684,
					99.4808772601294
				],
				[
					75.07986413489684,
					103.2348131854838
				],
				[
					75.07986413489684,
					106.98889231431431
				],
				[
					75.07986413489684,
					112.6197962023459
				],
				[
					75.07986413489684,
					116.37387533117642
				],
				[
					75.07986413489684,
					120.1278112565308
				],
				[
					75.07986413489684,
					123.8817471818852
				],
				[
					75.07986413489684,
					125.75885834803867
				],
				[
					76.95697530105066,
					129.5127942733931
				],
				[
					76.95697530105066,
					133.26673019874747
				],
				[
					76.95697530105066,
					135.1438413649008
				],
				[
					76.95697530105066,
					138.8977772902552
				],
				[
					76.95697530105066,
					142.65171321560956
				],
				[
					76.95697530105066,
					144.52882438176292
				],
				[
					78.83380006025122,
					148.2827603071173
				],
				[
					78.83380006025122,
					153.91380739862515
				],
				[
					78.83380006025122,
					155.79077536130237
				],
				[
					78.83380006025122,
					157.66774332397952
				],
				[
					78.83380006025122,
					165.17575837816446
				],
				[
					78.83380006025122,
					167.05272634084164
				],
				[
					78.83380006025122,
					170.80666226619604
				],
				[
					80.71091122640505,
					174.56074139502655
				],
				[
					80.71091122640505,
					178.31467732038095
				],
				[
					80.71091122640505,
					182.06875644921163
				],
				[
					80.71091122640505,
					183.94572441188882
				],
				[
					80.71091122640505,
					187.69966033724322
				],
				[
					80.71091122640505,
					191.45373946607376
				],
				[
					80.71091122640505,
					193.3307074287509
				],
				[
					80.71091122640505,
					195.20767539142813
				],
				[
					80.71091122640505,
					200.83872248293585
				],
				[
					80.71091122640505,
					202.71569044561303
				],
				[
					80.71091122640505,
					204.59265840829022
				],
				[
					80.71091122640505,
					208.34659433364462
				],
				[
					80.71091122640505,
					210.22370549979811
				],
				[
					80.71091122640505,
					213.97764142515248
				],
				[
					80.71091122640505,
					215.8546093878297
				],
				[
					80.71091122640505,
					219.6086885166602
				],
				[
					80.71091122640505,
					221.48565647933745
				],
				[
					80.71091122640505,
					223.36262444201458
				],
				[
					80.71091122640505,
					225.2395924046918
				],
				[
					80.71091122640505,
					227.11656036736898
				],
				[
					80.71091122640505,
					228.99367153352233
				],
				[
					80.71091122640505,
					230.87063949619954
				],
				[
					80.71091122640505,
					232.74760745887667
				],
				[
					80.71091122640505,
					234.6245754215539
				],
				[
					80.71091122640505,
					236.50154338423104
				],
				[
					80.71091122640505,
					238.37865455038457
				],
				[
					80.71091122640505,
					240.25562251306178
				],
				[
					80.71091122640505,
					242.13259047573897
				],
				[
					80.71091122640505,
					244.00955843841615
				],
				[
					80.71091122640505,
					245.88652640109336
				],
				[
					80.71091122640505,
					247.7636375672467
				],
				[
					80.71091122640505,
					249.64060552992387
				],
				[
					80.71091122640505,
					251.51757349260106
				],
				[
					80.71091122640505,
					253.39454145527827
				],
				[
					80.71091122640505,
					255.27150941795546
				],
				[
					80.71091122640505,
					257.14862058410876
				],
				[
					80.71091122640505,
					260.9025565094632
				],
				[
					80.71091122640505,
					262.77952447214034
				],
				[
					80.71091122640505,
					264.65649243481755
				],
				[
					80.71091122640505,
					266.53360360097105
				],
				[
					80.71091122640505,
					268.41057156364826
				],
				[
					80.71091122640505,
					270.2875395263254
				],
				[
					80.71091122640505,
					272.16450748900263
				],
				[
					80.71091122640505,
					274.04147545167984
				],
				[
					80.71091122640505,
					275.91858661783317
				],
				[
					82.58773598560559,
					277.7955545805104
				],
				[
					82.58773598560559,
					279.67252254318754
				],
				[
					82.58773598560559,
					281.54949050586475
				],
				[
					82.58773598560559,
					283.4264584685419
				],
				[
					84.46484715175943,
					285.3035696346953
				],
				[
					84.46484715175943,
					287.1805375973725
				],
				[
					84.46484715175943,
					289.0575055600496
				],
				[
					84.46484715175943,
					290.9344735227268
				],
				[
					84.46484715175943,
					290.9344735227268
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "kqopo0YbSJSZaZQFeYqEC",
			"type": "freedraw",
			"x": 5664.559874812169,
			"y": -1154.5754671298978,
			"width": 95.72665492782257,
			"height": 3.754079128830696,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3x",
			"roundness": null,
			"seed": 404515167,
			"version": 302,
			"versionNonce": 1754606161,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.8768247592005536,
					0
				],
				[
					3.7539359253543796,
					0
				],
				[
					7.507871850708759,
					0
				],
				[
					11.26180777606314,
					0
				],
				[
					18.76996603372389,
					0
				],
				[
					24.400726718278822,
					0
				],
				[
					28.154949050586477,
					0
				],
				[
					31.908884975940854,
					0
				],
				[
					33.78570973514141,
					0
				],
				[
					35.66282090129524,
					0
				],
				[
					37.53993206744778,
					0
				],
				[
					39.41675682664962,
					0
				],
				[
					41.293867992802156,
					0
				],
				[
					43.170692752003994,
					0
				],
				[
					45.04780391815654,
					0
				],
				[
					46.92491508431037,
					0
				],
				[
					48.80173984351092,
					0
				],
				[
					50.678851009664754,
					0
				],
				[
					52.55567576886529,
					-1.8769679626771898
				],
				[
					54.43278693501913,
					-1.8769679626771898
				],
				[
					56.309898101172955,
					-1.8769679626771898
				],
				[
					58.1867228603735,
					-1.8769679626771898
				],
				[
					61.94065878572789,
					-1.8769679626771898
				],
				[
					63.81776995188171,
					-1.8769679626771898
				],
				[
					65.69488111803426,
					-1.8769679626771898
				],
				[
					67.5717058772361,
					-1.8769679626771898
				],
				[
					69.44881704338864,
					-1.8769679626771898
				],
				[
					71.32564180259048,
					-1.8769679626771898
				],
				[
					73.20275296874301,
					-1.8769679626771898
				],
				[
					75.07986413489685,
					-1.8769679626771898
				],
				[
					76.95668889409741,
					-1.8769679626771898
				],
				[
					78.83380006025122,
					-1.8769679626771898
				],
				[
					80.71062481945178,
					0
				],
				[
					82.5877359856056,
					0
				],
				[
					84.46484715175944,
					0
				],
				[
					86.34167191095999,
					0
				],
				[
					88.2187830771138,
					0
				],
				[
					90.09560783631436,
					0
				],
				[
					91.9727190024682,
					1.877111166153506
				],
				[
					93.84983016862074,
					1.877111166153506
				],
				[
					95.72665492782257,
					1.877111166153506
				],
				[
					95.72665492782257,
					1.877111166153506
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "qdsk35W3lh411OYfTT61-",
			"type": "arrow",
			"x": 5271.753978771753,
			"y": -1799.2958651929816,
			"width": 0,
			"height": 269.333292643229,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3y",
			"roundness": {
				"type": 2
			},
			"seed": 346416511,
			"version": 87,
			"versionNonce": 570275889,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					269.333292643229
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "hQwOWGAQ",
			"type": "text",
			"x": 5381.087067964461,
			"y": -1695.295926228138,
			"width": 746.4237670898438,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b3z",
			"roundness": null,
			"seed": 384490911,
			"version": 80,
			"versionNonce": 517573137,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"text": "Break the Laplacian matrix into block form",
			"rawText": "Break the Laplacian matrix into block form",
			"fontSize": 36,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Break the Laplacian matrix into block form",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "FGJaz-EbY-U6hx3UEqEae",
			"type": "arrow",
			"x": 5249.7435109040825,
			"y": -1102.0195765558178,
			"width": 1.8768247592011937,
			"height": 360.38336216785444,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b40",
			"roundness": {
				"type": 2
			},
			"seed": 1377554879,
			"version": 333,
			"versionNonce": 404758513,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.8768247592011937,
					360.38336216785444
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "dDzHZFlSi2V5KgOK1zwFm",
			"type": "freedraw",
			"x": 4728.466818712374,
			"y": -504.0053594401322,
			"width": 87.2802990957752,
			"height": 132.3281746156707,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b41",
			"roundness": null,
			"seed": 1062814175,
			"version": 218,
			"versionNonce": 1004075473,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157846
				],
				[
					0,
					-5.630903888031569
				],
				[
					0,
					-11.261807776063138
				],
				[
					2.8154519440157846,
					-16.89292646930902
				],
				[
					5.630903888031569,
					-28.154949050586474
				],
				[
					8.446355832047352,
					-36.601304882633826
				],
				[
					11.262022581277451,
					-45.0478755198955
				],
				[
					14.077474525293237,
					-53.494231351942844
				],
				[
					16.89292646930902,
					-64.7562539332203
				],
				[
					19.708378413324805,
					-76.01827651449776
				],
				[
					25.339497106570686,
					-87.2802990957752
				],
				[
					28.154949050586474,
					-98.54232167705266
				],
				[
					30.970400994602254,
					-106.98867750910001
				],
				[
					36.601304882633826,
					-112.6197962023459
				],
				[
					36.601304882633826,
					-118.25070009037745
				],
				[
					39.41697163186393,
					-121.06615203439323
				],
				[
					42.232423575879714,
					-123.88160397840902
				],
				[
					42.232423575879714,
					-126.69727072763912
				],
				[
					42.232423575879714,
					-129.5127226716549
				],
				[
					45.0478755198955,
					-129.5127226716549
				],
				[
					45.0478755198955,
					-132.3281746156707
				],
				[
					47.86332746391128,
					-132.3281746156707
				],
				[
					50.67877940792706,
					-132.3281746156707
				],
				[
					50.67877940792706,
					-123.88160397840902
				],
				[
					56.30989810117295,
					-118.25070009037745
				],
				[
					56.30989810117295,
					-109.80412945311578
				],
				[
					61.94080198920451,
					-98.54232167705266
				],
				[
					64.7562539332203,
					-87.2802990957752
				],
				[
					70.38737262646619,
					-76.01827651449776
				],
				[
					73.20282457048197,
					-61.94080198920451
				],
				[
					76.01827651449776,
					-53.494231351942844
				],
				[
					78.83372845851353,
					-42.232423575879714
				],
				[
					81.64939520774364,
					-30.970400994602254
				],
				[
					84.46484715175943,
					-25.339282301356377
				],
				[
					84.46484715175943,
					-22.52383035734059
				],
				[
					87.2802990957752,
					-19.708378413324805
				],
				[
					87.2802990957752,
					-16.89292646930902
				],
				[
					87.2802990957752,
					-14.077474525293237
				],
				[
					87.2802990957752,
					-11.261807776063138
				],
				[
					87.2802990957752,
					-11.261807776063138
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "Q_h1jmadckxhRXTVy-7IF",
			"type": "freedraw",
			"x": 4742.544293237668,
			"y": -563.1307094853207,
			"width": 61.94080198920451,
			"height": 2.8154519440157846,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b42",
			"roundness": null,
			"seed": 1605611007,
			"version": 197,
			"versionNonce": 186357681,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157846
				],
				[
					2.815451944015784,
					-2.8154519440157846
				],
				[
					5.630903888031568,
					-2.8154519440157846
				],
				[
					11.262022581277451,
					-2.8154519440157846
				],
				[
					14.077474525293235,
					-2.8154519440157846
				],
				[
					16.89292646930902,
					-2.8154519440157846
				],
				[
					22.523830357340586,
					-2.8154519440157846
				],
				[
					28.15494905058647,
					-2.8154519440157846
				],
				[
					30.970400994602254,
					-2.8154519440157846
				],
				[
					36.60130488263382,
					-2.8154519440157846
				],
				[
					42.23242357587971,
					-2.8154519440157846
				],
				[
					45.04787551989549,
					-2.8154519440157846
				],
				[
					47.863327463911276,
					-2.8154519440157846
				],
				[
					50.67877940792705,
					-2.8154519440157846
				],
				[
					53.49444615715715,
					-2.8154519440157846
				],
				[
					56.30989810117294,
					-2.8154519440157846
				],
				[
					59.125350045188725,
					-2.8154519440157846
				],
				[
					61.94080198920451,
					-2.8154519440157846
				],
				[
					61.94080198920451,
					-2.8154519440157846
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "Y6DI8vfRmusI7blYDJuaZ",
			"type": "freedraw",
			"x": 4886.134490434615,
			"y": -523.7137378534569,
			"width": 61.94080198920451,
			"height": 98.54232167705266,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b43",
			"roundness": null,
			"seed": 1043043871,
			"version": 256,
			"versionNonce": 2014280081,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157846
				],
				[
					0,
					-5.630903888031569
				],
				[
					-5.630903888031568,
					-5.630903888031569
				],
				[
					-5.630903888031568,
					-8.446570637261667
				],
				[
					-8.446570637261667,
					-8.446570637261667
				],
				[
					-11.262022581277451,
					-8.446570637261667
				],
				[
					-14.077474525293235,
					-8.446570637261667
				],
				[
					-16.89292646930902,
					-11.262022581277451
				],
				[
					-19.7083784133248,
					-11.262022581277451
				],
				[
					-25.339497106570683,
					-11.262022581277451
				],
				[
					-28.15494905058647,
					-11.262022581277451
				],
				[
					-33.78585293861804,
					-5.630903888031569
				],
				[
					-36.60151968784813,
					-2.8154519440157846
				],
				[
					-39.41697163186392,
					0
				],
				[
					-45.04787551989549,
					2.8154519440157846
				],
				[
					-47.863327463911276,
					5.630903888031569
				],
				[
					-50.678994213141365,
					11.262022581277451
				],
				[
					-53.49444615715715,
					11.262022581277451
				],
				[
					-53.49444615715715,
					16.89292646930902
				],
				[
					-56.30989810117294,
					16.89292646930902
				],
				[
					-59.125350045188725,
					22.524045162554902
				],
				[
					-59.125350045188725,
					25.339497106570686
				],
				[
					-61.94080198920451,
					25.339497106570686
				],
				[
					-61.94080198920451,
					28.154949050586474
				],
				[
					-61.94080198920451,
					30.970400994602258
				],
				[
					-61.94080198920451,
					33.78585293861804
				],
				[
					-61.94080198920451,
					36.60151968784814
				],
				[
					-61.94080198920451,
					39.41697163186393
				],
				[
					-61.94080198920451,
					42.232423575879714
				],
				[
					-61.94080198920451,
					45.04787551989549
				],
				[
					-61.94080198920451,
					47.863327463911276
				],
				[
					-61.94080198920451,
					50.67899421314137
				],
				[
					-59.125350045188725,
					53.49444615715716
				],
				[
					-56.30989810117294,
					59.125350045188725
				],
				[
					-53.49444615715715,
					64.75646873843462
				],
				[
					-50.678994213141365,
					70.38737262646619
				],
				[
					-50.678994213141365,
					73.20282457048197
				],
				[
					-47.863327463911276,
					76.01827651449776
				],
				[
					-45.04787551989549,
					78.83394326372786
				],
				[
					-42.23242357587971,
					78.83394326372786
				],
				[
					-42.23242357587971,
					81.64939520774364
				],
				[
					-42.23242357587971,
					84.46484715175943
				],
				[
					-42.23242357587971,
					87.2802990957752
				],
				[
					-39.41697163186392,
					87.2802990957752
				],
				[
					-36.60151968784813,
					87.2802990957752
				],
				[
					-33.78585293861804,
					87.2802990957752
				],
				[
					-30.970400994602254,
					87.2802990957752
				],
				[
					-28.15494905058647,
					84.46484715175943
				],
				[
					-28.15494905058647,
					81.64939520774364
				],
				[
					-25.339497106570683,
					81.64939520774364
				],
				[
					-25.339497106570683,
					78.83394326372786
				],
				[
					-22.524045162554902,
					76.01827651449776
				],
				[
					-22.524045162554902,
					73.20282457048197
				],
				[
					-22.524045162554902,
					67.5719206824504
				],
				[
					-19.7083784133248,
					64.75646873843462
				],
				[
					-19.7083784133248,
					61.940801989204516
				],
				[
					-19.7083784133248,
					59.125350045188725
				],
				[
					-19.7083784133248,
					56.30989810117295
				],
				[
					-16.89292646930902,
					53.49444615715716
				],
				[
					-16.89292646930902,
					50.67899421314137
				],
				[
					-16.89292646930902,
					47.863327463911276
				],
				[
					-16.89292646930902,
					45.04787551989549
				],
				[
					-16.89292646930902,
					50.67899421314137
				],
				[
					-16.89292646930902,
					56.30989810117295
				],
				[
					-16.89292646930902,
					59.125350045188725
				],
				[
					-16.89292646930902,
					61.940801989204516
				],
				[
					-16.89292646930902,
					64.75646873843462
				],
				[
					-16.89292646930902,
					67.5719206824504
				],
				[
					-16.89292646930902,
					70.38737262646619
				],
				[
					-16.89292646930902,
					73.20282457048197
				],
				[
					-16.89292646930902,
					76.01827651449776
				],
				[
					-16.89292646930902,
					78.83394326372786
				],
				[
					-16.89292646930902,
					81.64939520774364
				],
				[
					-16.89292646930902,
					84.46484715175943
				],
				[
					-16.89292646930902,
					87.2802990957752
				],
				[
					-16.89292646930902,
					87.2802990957752
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "97dmotDLWVHqw5IlFv51U",
			"type": "freedraw",
			"x": 4849.532970746767,
			"y": -473.0347436403151,
			"width": 25.339497106570686,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b44",
			"roundness": null,
			"seed": 833714751,
			"version": 189,
			"versionNonce": 1139548017,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8156667492300986,
					0
				],
				[
					5.631118693245884,
					0
				],
				[
					8.446570637261669,
					0
				],
				[
					11.262022581277451,
					0
				],
				[
					14.077474525293237,
					0
				],
				[
					16.893141274523337,
					0
				],
				[
					19.70859321853912,
					0
				],
				[
					22.524045162554902,
					0
				],
				[
					25.339497106570686,
					0
				],
				[
					25.339497106570686,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "pliIMSDGUssomwTYI1n_S",
			"type": "freedraw",
			"x": 4903.027416903925,
			"y": -515.2671672161953,
			"width": 50.67877940792706,
			"height": 95.72665492782257,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b45",
			"roundness": null,
			"seed": 1596316255,
			"version": 207,
			"versionNonce": 486082897,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.63090388803157
				],
				[
					0,
					14.077474525293239
				],
				[
					-2.815451944015784,
					25.33928230135638
				],
				[
					-2.815451944015784,
					36.60130488263383
				],
				[
					-2.815451944015784,
					45.0478755198955
				],
				[
					-2.815451944015784,
					56.309898101172955
				],
				[
					-2.815451944015784,
					64.75625393322031
				],
				[
					-5.630903888031568,
					73.20282457048198
				],
				[
					-5.630903888031568,
					81.64918040252934
				],
				[
					-5.630903888031568,
					84.46484715175944
				],
				[
					-8.446355832047352,
					87.28029909577522
				],
				[
					-8.446355832047352,
					90.095751039791
				],
				[
					-8.446355832047352,
					92.91120298380679
				],
				[
					-8.446355832047352,
					95.72665492782257
				],
				[
					-5.630903888031568,
					95.72665492782257
				],
				[
					0,
					95.72665492782257
				],
				[
					2.815451944015784,
					92.91120298380679
				],
				[
					11.26202258127745,
					92.91120298380679
				],
				[
					16.892926469309018,
					90.095751039791
				],
				[
					22.5240451625549,
					90.095751039791
				],
				[
					25.339497106570683,
					90.095751039791
				],
				[
					30.97040099460225,
					90.095751039791
				],
				[
					33.78606774383235,
					90.095751039791
				],
				[
					36.60151968784813,
					90.095751039791
				],
				[
					36.60151968784813,
					87.28029909577522
				],
				[
					39.41697163186392,
					87.28029909577522
				],
				[
					42.23242357587971,
					87.28029909577522
				],
				[
					42.23242357587971,
					87.28029909577522
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "YjPYWWcgL3iMgSQMlJBzv",
			"type": "freedraw",
			"x": 4998.75428663696,
			"y": -568.7616133733525,
			"width": 33.78585293861804,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b46",
			"roundness": null,
			"seed": 2069444223,
			"version": 189,
			"versionNonce": 2089662257,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8154519440157846,
					0
				],
				[
					5.630903888031569,
					0
				],
				[
					11.262022581277451,
					0
				],
				[
					14.077474525293237,
					0
				],
				[
					19.708378413324805,
					0
				],
				[
					22.524045162554902,
					0
				],
				[
					25.339497106570686,
					0
				],
				[
					28.154949050586474,
					0
				],
				[
					30.970400994602254,
					0
				],
				[
					33.78585293861804,
					0
				],
				[
					33.78585293861804,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "NumOPz1j8j6nqTB4l-Lrk",
			"type": "freedraw",
			"x": 5007.200857274223,
			"y": -523.7137378534569,
			"width": 30.970400994602254,
			"height": 5.630903888031569,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b47",
			"roundness": null,
			"seed": 1292635807,
			"version": 191,
			"versionNonce": 1158785297,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.815451944015784,
					0
				],
				[
					5.630903888031568,
					0
				],
				[
					8.446355832047352,
					-2.8154519440157846
				],
				[
					11.261807776063137,
					-2.8154519440157846
				],
				[
					14.077474525293235,
					-2.8154519440157846
				],
				[
					16.89292646930902,
					-2.8154519440157846
				],
				[
					19.7083784133248,
					-2.8154519440157846
				],
				[
					22.523830357340586,
					-2.8154519440157846
				],
				[
					22.523830357340586,
					-5.630903888031569
				],
				[
					25.339282301356373,
					-5.630903888031569
				],
				[
					28.15494905058647,
					-5.630903888031569
				],
				[
					30.970400994602254,
					-5.630903888031569
				],
				[
					30.970400994602254,
					-5.630903888031569
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "nK68GHw4B04mwUzhYuFy8",
			"type": "freedraw",
			"x": 5201.469833879098,
			"y": -557.499590792075,
			"width": 95.72686973303686,
			"height": 2.8154519440157846,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b48",
			"roundness": null,
			"seed": 1861149375,
			"version": 195,
			"versionNonce": 536633073,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8156667492300986,
					0
				],
				[
					8.446570637261669,
					0
				],
				[
					11.262022581277451,
					0
				],
				[
					16.893141274523337,
					0
				],
				[
					28.154949050586474,
					0
				],
				[
					36.60151968784814,
					0
				],
				[
					47.86354226912559,
					0
				],
				[
					53.49444615715716,
					0
				],
				[
					64.75646873843462,
					0
				],
				[
					70.38737262646619,
					0
				],
				[
					76.01849131971207,
					0
				],
				[
					81.64939520774364,
					2.8154519440157846
				],
				[
					90.09596584500531,
					2.8154519440157846
				],
				[
					92.91141778902109,
					2.8154519440157846
				],
				[
					95.72686973303686,
					2.8154519440157846
				],
				[
					95.72686973303686,
					2.8154519440157846
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "gXos_x_2qJqYvU7Y0Hcln",
			"type": "freedraw",
			"x": 5373.215194931848,
			"y": -489.92788491483884,
			"width": 90.095751039791,
			"height": 171.74514624753462,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b49",
			"roundness": null,
			"seed": 1369584351,
			"version": 238,
			"versionNonce": 466966737,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-5.630903888031569
				],
				[
					0,
					-11.261807776063138
				],
				[
					0,
					-19.708378413324805
				],
				[
					5.630903888031569,
					-30.970400994602254
				],
				[
					5.630903888031569,
					-39.41675682664961
				],
				[
					11.261807776063138,
					-47.86332746391128
				],
				[
					11.261807776063138,
					-56.30989810117295
				],
				[
					14.077474525293237,
					-64.7562539332203
				],
				[
					16.89292646930902,
					-73.20282457048197
				],
				[
					19.708378413324805,
					-81.64918040252932
				],
				[
					19.708378413324805,
					-87.2802990957752
				],
				[
					19.708378413324805,
					-90.095751039791
				],
				[
					22.52383035734059,
					-95.72665492782257
				],
				[
					22.52383035734059,
					-104.17322556508422
				],
				[
					25.339282301356377,
					-106.98867750910001
				],
				[
					25.339282301356377,
					-112.6197962023459
				],
				[
					28.154949050586474,
					-118.25070009037745
				],
				[
					28.154949050586474,
					-123.88160397840902
				],
				[
					30.970400994602254,
					-123.88160397840902
				],
				[
					33.78585293861804,
					-129.5127226716549
				],
				[
					33.78585293861804,
					-132.3281746156707
				],
				[
					33.78585293861804,
					-135.14362655968648
				],
				[
					33.78585293861804,
					-137.95907850370224
				],
				[
					36.601304882633826,
					-137.95907850370224
				],
				[
					36.601304882633826,
					-140.77474525293238
				],
				[
					39.41675682664961,
					-143.59019719694814
				],
				[
					45.0478755198955,
					-152.0365530289955
				],
				[
					47.86332746391128,
					-157.66767172224138
				],
				[
					53.494231351942844,
					-160.48312366625717
				],
				[
					53.494231351942844,
					-163.29857561027293
				],
				[
					53.494231351942844,
					-166.11402755428873
				],
				[
					56.30989810117295,
					-166.11402755428873
				],
				[
					56.30989810117295,
					-168.92969430351886
				],
				[
					59.125350045188725,
					-168.92969430351886
				],
				[
					59.125350045188725,
					-171.74514624753462
				],
				[
					61.94080198920451,
					-171.74514624753462
				],
				[
					61.94080198920451,
					-168.92969430351886
				],
				[
					61.94080198920451,
					-163.29857561027293
				],
				[
					67.57170587723608,
					-154.8522197782256
				],
				[
					67.57170587723608,
					-143.59019719694814
				],
				[
					70.38737262646619,
					-132.3281746156707
				],
				[
					73.20282457048197,
					-121.06615203439323
				],
				[
					76.01827651449776,
					-109.80412945311578
				],
				[
					76.01827651449776,
					-98.54232167705266
				],
				[
					78.83372845851353,
					-92.91120298380677
				],
				[
					81.64918040252932,
					-81.64918040252932
				],
				[
					84.46484715175943,
					-76.01827651449776
				],
				[
					84.46484715175943,
					-70.38737262646619
				],
				[
					84.46484715175943,
					-61.94080198920451
				],
				[
					84.46484715175943,
					-56.30989810117295
				],
				[
					84.46484715175943,
					-50.67877940792706
				],
				[
					87.2802990957752,
					-42.232423575879714
				],
				[
					87.2802990957752,
					-36.601304882633826
				],
				[
					87.2802990957752,
					-30.970400994602254
				],
				[
					90.095751039791,
					-22.52383035734059
				],
				[
					90.095751039791,
					-16.89292646930902
				],
				[
					90.095751039791,
					-14.077474525293237
				],
				[
					90.095751039791,
					-11.261807776063138
				],
				[
					90.095751039791,
					-8.446355832047352
				],
				[
					90.095751039791,
					-8.446355832047352
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "Ztfyavy9WcfgEXSV8BJXf",
			"type": "freedraw",
			"x": 5398.554477233203,
			"y": -563.1307094853207,
			"width": 53.49444615715716,
			"height": 8.446355832047352,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4A",
			"roundness": null,
			"seed": 2109112063,
			"version": 192,
			"versionNonce": 171185841,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.631118693245884,
					-2.8154519440157837
				],
				[
					14.077474525293237,
					-2.8154519440157837
				],
				[
					22.524045162554902,
					-5.630903888031567
				],
				[
					28.154949050586474,
					-5.630903888031567
				],
				[
					30.97061579981657,
					-5.630903888031567
				],
				[
					33.786067743832355,
					-5.630903888031567
				],
				[
					36.60151968784814,
					-5.630903888031567
				],
				[
					39.41697163186393,
					-5.630903888031567
				],
				[
					42.232423575879714,
					-8.446355832047352
				],
				[
					45.048090325109804,
					-8.446355832047352
				],
				[
					47.86354226912559,
					-8.446355832047352
				],
				[
					50.67899421314137,
					-8.446355832047352
				],
				[
					53.49444615715716,
					-8.446355832047352
				],
				[
					53.49444615715716,
					-8.446355832047352
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "IqtWj7-3-WJpX8xe7YKah",
			"type": "freedraw",
			"x": 5407.001047870465,
			"y": -698.274336045007,
			"width": 78.83394326372786,
			"height": 45.0478755198955,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4B",
			"roundness": null,
			"seed": 363611935,
			"version": 202,
			"versionNonce": 499128465,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.8154519440157846
				],
				[
					2.815451944015785,
					0
				],
				[
					14.077474525293237,
					-8.44657063726167
				],
				[
					22.524045162554906,
					-11.262022581277453
				],
				[
					28.154949050586474,
					-14.077474525293239
				],
				[
					36.601519687848146,
					-19.708593218539125
				],
				[
					42.23242357587972,
					-22.524045162554906
				],
				[
					50.67899421314138,
					-25.33949710657069
				],
				[
					50.67899421314138,
					-28.154949050586477
				],
				[
					53.49444615715717,
					-28.154949050586477
				],
				[
					56.30989810117295,
					-28.154949050586477
				],
				[
					59.12535004518873,
					-25.33949710657069
				],
				[
					61.94080198920452,
					-19.708593218539125
				],
				[
					64.75646873843462,
					-16.89314127452334
				],
				[
					64.75646873843462,
					-11.262022581277453
				],
				[
					67.57192068245041,
					-5.631118693245884
				],
				[
					70.38737262646619,
					0
				],
				[
					70.38737262646619,
					2.8154519440157846
				],
				[
					73.20282457048198,
					8.446355832047354
				],
				[
					76.01827651449777,
					11.261807776063138
				],
				[
					76.01827651449777,
					14.077474525293239
				],
				[
					78.83394326372786,
					16.89292646930902
				],
				[
					78.83394326372786,
					16.89292646930902
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "GzCZGDI0jE3Q6qpfVQAhO",
			"type": "freedraw",
			"x": 5556.222363760659,
			"y": -658.8575792183576,
			"width": 70.38737262646681,
			"height": 152.0367678342098,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4C",
			"roundness": null,
			"seed": 401869631,
			"version": 229,
			"versionNonce": 1211162225,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157837
				],
				[
					0,
					2.8156667492300977
				],
				[
					0,
					8.446570637261665
				],
				[
					0,
					19.708593218539114
				],
				[
					0,
					25.339497106570683
				],
				[
					0,
					36.601519687848125
				],
				[
					0,
					47.86354226912558
				],
				[
					0,
					59.12556485040303
				],
				[
					0,
					67.57192068245038
				],
				[
					0,
					78.83394326372783
				],
				[
					0,
					84.4648471517594
				],
				[
					0,
					90.09596584500528
				],
				[
					0,
					95.72686973303685
				],
				[
					0,
					98.54232167705263
				],
				[
					0,
					104.17344037029851
				],
				[
					0,
					106.9888923143143
				],
				[
					0,
					112.61979620234587
				],
				[
					0,
					115.43546295157597
				],
				[
					0,
					118.25091489559175
				],
				[
					0,
					121.06636683960754
				],
				[
					0,
					123.88181878362332
				],
				[
					0,
					126.69727072763911
				],
				[
					0,
					129.5129374768692
				],
				[
					0,
					132.32838942088497
				],
				[
					0,
					135.14384136490077
				],
				[
					0,
					137.95929330891653
				],
				[
					0,
					140.77474525293232
				],
				[
					0,
					143.59041200216242
				],
				[
					0,
					146.40586394617821
				],
				[
					0,
					149.221315890194
				],
				[
					5.630903888031568,
					149.221315890194
				],
				[
					8.446355832047352,
					149.221315890194
				],
				[
					14.077474525293235,
					149.221315890194
				],
				[
					19.7083784133248,
					149.221315890194
				],
				[
					25.339282301356373,
					149.221315890194
				],
				[
					28.15494905058647,
					149.221315890194
				],
				[
					30.97040099460225,
					149.221315890194
				],
				[
					33.785852938618035,
					149.221315890194
				],
				[
					36.60130488263382,
					149.221315890194
				],
				[
					39.4167568266496,
					149.221315890194
				],
				[
					45.04787551989549,
					149.221315890194
				],
				[
					47.863327463911276,
					149.221315890194
				],
				[
					50.67877940792705,
					149.221315890194
				],
				[
					53.49423135194284,
					149.221315890194
				],
				[
					56.30989810117294,
					149.221315890194
				],
				[
					64.75625393322028,
					149.221315890194
				],
				[
					67.57170587723671,
					149.221315890194
				],
				[
					70.38737262646681,
					149.221315890194
				],
				[
					70.38737262646681,
					149.221315890194
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "DnElrvYrXVCGOlxgHad4Q",
			"type": "freedraw",
			"x": 5660.395589325744,
			"y": -523.7137378534569,
			"width": 92.91120298380677,
			"height": 67.5719206824504,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4D",
			"roundness": null,
			"seed": 1626229599,
			"version": 216,
			"versionNonce": 1481500753,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8154519440157846,
					2.8154519440157846
				],
				[
					2.8154519440157846,
					5.630903888031569
				],
				[
					2.8154519440157846,
					8.446570637261669
				],
				[
					2.8154519440157846,
					11.262022581277451
				],
				[
					5.631118693245884,
					16.89292646930902
				],
				[
					5.631118693245884,
					19.708378413324805
				],
				[
					5.631118693245884,
					25.339497106570686
				],
				[
					8.446355832047352,
					30.970400994602254
				],
				[
					8.446355832047352,
					33.78585293861804
				],
				[
					8.446355832047352,
					36.60151968784814
				],
				[
					8.446355832047352,
					39.41697163186393
				],
				[
					8.446355832047352,
					42.232423575879714
				],
				[
					8.446355832047352,
					45.0478755198955
				],
				[
					8.446355832047352,
					47.86332746391128
				],
				[
					11.262022581277451,
					47.86332746391128
				],
				[
					11.262022581277451,
					50.67899421314137
				],
				[
					11.262022581277451,
					53.49444615715716
				],
				[
					14.07768933050755,
					53.49444615715716
				],
				[
					14.07768933050755,
					59.125350045188725
				],
				[
					14.07768933050755,
					61.94080198920451
				],
				[
					16.89292646930902,
					61.94080198920451
				],
				[
					16.89292646930902,
					64.75646873843462
				],
				[
					19.70859321853912,
					67.5719206824504
				],
				[
					22.52383035734059,
					67.5719206824504
				],
				[
					25.339497106570686,
					67.5719206824504
				],
				[
					28.15516385580079,
					67.5719206824504
				],
				[
					30.970400994602254,
					67.5719206824504
				],
				[
					36.601304882633826,
					67.5719206824504
				],
				[
					42.23263838109403,
					67.5719206824504
				],
				[
					45.0478755198955,
					67.5719206824504
				],
				[
					56.31011290638726,
					67.5719206824504
				],
				[
					64.7562539332203,
					64.75646873843462
				],
				[
					73.20282457048197,
					64.75646873843462
				],
				[
					81.64939520774364,
					64.75646873843462
				],
				[
					87.2802990957752,
					61.94080198920451
				],
				[
					90.09596584500531,
					61.94080198920451
				],
				[
					92.91120298380677,
					61.94080198920451
				],
				[
					92.91120298380677,
					61.94080198920451
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "qc7TPD9-m6P4-K4B3ujl_",
			"type": "freedraw",
			"x": 5758.938125808012,
			"y": -518.0828339654256,
			"width": 61.94080198920451,
			"height": 76.01827651449776,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4E",
			"roundness": null,
			"seed": 1827374975,
			"version": 247,
			"versionNonce": 1475262001,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.631118693245884
				],
				[
					2.81523713880147,
					11.262022581277451
				],
				[
					2.81523713880147,
					14.077474525293237
				],
				[
					2.81523713880147,
					19.70859321853912
				],
				[
					2.81523713880147,
					25.339497106570686
				],
				[
					5.630903888031568,
					28.154949050586474
				],
				[
					5.630903888031568,
					30.97061579981657
				],
				[
					8.446141026833038,
					30.97061579981657
				],
				[
					8.446141026833038,
					33.786067743832355
				],
				[
					8.446141026833038,
					36.60151968784814
				],
				[
					11.261807776063137,
					39.41697163186393
				],
				[
					11.261807776063137,
					42.232423575879714
				],
				[
					14.077474525293235,
					42.232423575879714
				],
				[
					14.077474525293235,
					45.048090325109804
				],
				[
					16.892711664094705,
					47.86354226912559
				],
				[
					19.7083784133248,
					47.86354226912559
				],
				[
					22.523615552126273,
					50.67899421314137
				],
				[
					22.523615552126273,
					53.49444615715716
				],
				[
					25.339282301356373,
					53.49444615715716
				],
				[
					28.15494905058647,
					53.49444615715716
				],
				[
					33.78585293861804,
					53.49444615715716
				],
				[
					36.601090077419514,
					56.30989810117295
				],
				[
					42.23242357587971,
					56.30989810117295
				],
				[
					45.04766071468117,
					56.30989810117295
				],
				[
					47.863327463911276,
					56.30989810117295
				],
				[
					50.67856460271275,
					56.30989810117295
				],
				[
					53.49423135194284,
					56.30989810117295
				],
				[
					56.30989810117294,
					56.30989810117295
				],
				[
					56.30989810117294,
					53.49444615715716
				],
				[
					56.30989810117294,
					50.67899421314137
				],
				[
					56.30989810117294,
					47.86354226912559
				],
				[
					56.30989810117294,
					45.048090325109804
				],
				[
					56.30989810117294,
					42.232423575879714
				],
				[
					56.30989810117294,
					36.60151968784814
				],
				[
					59.125135239974405,
					36.60151968784814
				],
				[
					59.125135239974405,
					30.97061579981657
				],
				[
					59.125135239974405,
					25.339497106570686
				],
				[
					59.125135239974405,
					22.524045162554902
				],
				[
					59.125135239974405,
					19.70859321853912
				],
				[
					59.125135239974405,
					16.893141274523337
				],
				[
					59.125135239974405,
					14.077474525293237
				],
				[
					59.125135239974405,
					8.446570637261669
				],
				[
					59.125135239974405,
					5.631118693245884
				],
				[
					59.125135239974405,
					2.8156667492300986
				],
				[
					59.125135239974405,
					0
				],
				[
					59.125135239974405,
					-2.8154519440157846
				],
				[
					59.125135239974405,
					-5.630903888031569
				],
				[
					59.125135239974405,
					-8.446355832047352
				],
				[
					59.125135239974405,
					-11.261807776063138
				],
				[
					61.94080198920451,
					-11.261807776063138
				],
				[
					61.94080198920451,
					-8.446355832047352
				],
				[
					61.94080198920451,
					0
				],
				[
					61.94080198920451,
					5.631118693245884
				],
				[
					61.94080198920451,
					11.262022581277451
				],
				[
					61.94080198920451,
					14.077474525293237
				],
				[
					61.94080198920451,
					22.524045162554902
				],
				[
					61.94080198920451,
					28.154949050586474
				],
				[
					61.94080198920451,
					33.786067743832355
				],
				[
					61.94080198920451,
					36.60151968784814
				],
				[
					61.94080198920451,
					42.232423575879714
				],
				[
					61.94080198920451,
					45.048090325109804
				],
				[
					61.94080198920451,
					47.86354226912559
				],
				[
					61.94080198920451,
					53.49444615715716
				],
				[
					61.94080198920451,
					56.30989810117295
				],
				[
					61.94080198920451,
					59.12556485040304
				],
				[
					61.94080198920451,
					61.94101679441883
				],
				[
					61.94080198920451,
					64.75646873843462
				],
				[
					61.94080198920451,
					64.75646873843462
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "bt2pAcfDEkNENHARcZtaw",
			"type": "freedraw",
			"x": 5905.343774948978,
			"y": -681.3814095756982,
			"width": 81.64918040252932,
			"height": 160.48312366625717,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4F",
			"roundness": null,
			"seed": 1512849311,
			"version": 228,
			"versionNonce": 704301073,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.815451944015784
				],
				[
					0,
					8.446355832047352
				],
				[
					0,
					16.892926469309018
				],
				[
					0,
					25.339497106570683
				],
				[
					0,
					36.60130488263382
				],
				[
					0,
					45.04787551989549
				],
				[
					0,
					53.49444615715715
				],
				[
					0,
					61.9408019892045
				],
				[
					0,
					67.57192068245038
				],
				[
					0,
					76.01827651449774
				],
				[
					0,
					84.46484715175941
				],
				[
					0,
					92.91120298380676
				],
				[
					0,
					98.54232167705264
				],
				[
					0,
					112.61979620234588
				],
				[
					0,
					115.43524814636167
				],
				[
					0,
					121.06615203439321
				],
				[
					0,
					126.69727072763911
				],
				[
					0,
					132.3281746156707
				],
				[
					0,
					137.95929330891656
				],
				[
					0,
					140.77474525293235
				],
				[
					0,
					143.5901971969481
				],
				[
					0,
					146.4056491409639
				],
				[
					0,
					149.2211010849797
				],
				[
					0,
					152.0367678342098
				],
				[
					0,
					154.8522197782256
				],
				[
					0,
					157.66767172224138
				],
				[
					2.81523713880147,
					157.66767172224138
				],
				[
					5.630903888031569,
					157.66767172224138
				],
				[
					8.446570637261669,
					157.66767172224138
				],
				[
					11.261807776063138,
					157.66767172224138
				],
				[
					16.892711664094705,
					157.66767172224138
				],
				[
					22.524045162554902,
					157.66767172224138
				],
				[
					28.154949050586474,
					157.66767172224138
				],
				[
					39.41675682664961,
					157.66767172224138
				],
				[
					42.232423575879714,
					157.66767172224138
				],
				[
					45.04766071468118,
					157.66767172224138
				],
				[
					47.86332746391128,
					157.66767172224138
				],
				[
					50.67899421314137,
					157.66767172224138
				],
				[
					53.494231351942844,
					157.66767172224138
				],
				[
					59.12513523997442,
					157.66767172224138
				],
				[
					61.94080198920451,
					157.66767172224138
				],
				[
					64.75646873843462,
					157.66767172224138
				],
				[
					67.57170587723608,
					157.66767172224138
				],
				[
					70.38737262646619,
					157.66767172224138
				],
				[
					73.20260976526765,
					157.66767172224138
				],
				[
					76.01827651449776,
					157.66767172224138
				],
				[
					78.83394326372786,
					160.48312366625717
				],
				[
					81.64918040252932,
					160.48312366625717
				],
				[
					81.64918040252932,
					160.48312366625717
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "5P_xOFp9QH9fmcZjcGxbB",
			"type": "freedraw",
			"x": 6026.410141788582,
			"y": -529.3446417414882,
			"width": 81.64918040252932,
			"height": 87.2802990957752,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4G",
			"roundness": null,
			"seed": 719385535,
			"version": 251,
			"versionNonce": 1751752177,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.8154519440157846
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					8.446355832047352
				],
				[
					0,
					11.261807776063138
				],
				[
					2.81523713880147,
					16.89292646930902
				],
				[
					5.630903888031569,
					22.52383035734059
				],
				[
					5.630903888031569,
					28.154949050586474
				],
				[
					8.44614102683304,
					30.970400994602254
				],
				[
					11.261807776063138,
					33.78585293861804
				],
				[
					14.077474525293237,
					36.601304882633826
				],
				[
					14.077474525293237,
					42.232423575879714
				],
				[
					16.892711664094705,
					45.0478755198955
				],
				[
					16.892711664094705,
					47.86332746391128
				],
				[
					19.708378413324805,
					50.67877940792706
				],
				[
					19.708378413324805,
					53.494231351942844
				],
				[
					22.523615552126277,
					59.125350045188725
				],
				[
					25.339282301356377,
					64.7562539332203
				],
				[
					28.154949050586474,
					67.57170587723608
				],
				[
					28.154949050586474,
					70.38737262646619
				],
				[
					30.97018618938795,
					70.38737262646619
				],
				[
					30.97018618938795,
					73.20282457048197
				],
				[
					33.78585293861804,
					76.01827651449776
				],
				[
					33.78585293861804,
					78.83372845851353
				],
				[
					36.601090077419514,
					78.83372845851353
				],
				[
					39.41675682664961,
					78.83372845851353
				],
				[
					42.232423575879714,
					78.83372845851353
				],
				[
					45.04766071468118,
					78.83372845851353
				],
				[
					47.86332746391128,
					76.01827651449776
				],
				[
					50.678564602712754,
					73.20282457048197
				],
				[
					56.30989810117295,
					70.38737262646619
				],
				[
					59.12513523997442,
					67.57170587723608
				],
				[
					61.94080198920451,
					64.7562539332203
				],
				[
					61.94080198920451,
					61.94080198920451
				],
				[
					61.94080198920451,
					59.125350045188725
				],
				[
					64.75603912800598,
					56.30989810117295
				],
				[
					67.57170587723608,
					53.494231351942844
				],
				[
					67.57170587723608,
					50.67877940792706
				],
				[
					67.57170587723608,
					47.86332746391128
				],
				[
					67.57170587723608,
					42.232423575879714
				],
				[
					67.57170587723608,
					39.41675682664961
				],
				[
					67.57170587723608,
					33.78585293861804
				],
				[
					70.38737262646619,
					30.970400994602254
				],
				[
					70.38737262646619,
					25.339282301356377
				],
				[
					70.38737262646619,
					19.708378413324805
				],
				[
					70.38737262646619,
					16.89292646930902
				],
				[
					70.38737262646619,
					11.261807776063138
				],
				[
					70.38737262646619,
					8.446355832047352
				],
				[
					70.38737262646619,
					5.630903888031569
				],
				[
					70.38737262646619,
					-2.8156667492300986
				],
				[
					70.38737262646619,
					-5.631118693245884
				],
				[
					70.38737262646619,
					-8.446570637261669
				],
				[
					73.20260976526765,
					-8.446570637261669
				],
				[
					73.20260976526765,
					-5.631118693245884
				],
				[
					73.20260976526765,
					-2.8156667492300986
				],
				[
					73.20260976526765,
					2.8154519440157846
				],
				[
					73.20260976526765,
					8.446355832047352
				],
				[
					73.20260976526765,
					16.89292646930902
				],
				[
					73.20260976526765,
					25.339282301356377
				],
				[
					73.20260976526765,
					30.970400994602254
				],
				[
					73.20260976526765,
					39.41675682664961
				],
				[
					73.20260976526765,
					45.0478755198955
				],
				[
					73.20260976526765,
					50.67877940792706
				],
				[
					73.20260976526765,
					56.30989810117295
				],
				[
					73.20260976526765,
					59.125350045188725
				],
				[
					73.20260976526765,
					64.7562539332203
				],
				[
					73.20260976526765,
					67.57170587723608
				],
				[
					73.20260976526765,
					70.38737262646619
				],
				[
					73.20260976526765,
					73.20282457048197
				],
				[
					76.01827651449776,
					73.20282457048197
				],
				[
					78.83351365329922,
					73.20282457048197
				],
				[
					81.64918040252932,
					70.38737262646619
				],
				[
					81.64918040252932,
					67.57170587723608
				],
				[
					81.64918040252932,
					67.57170587723608
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "8XZxi9FALIPvH8Nu3I338",
			"type": "freedraw",
			"x": 6136.214271241696,
			"y": -526.5291897974728,
			"width": 50.67899421314137,
			"height": 92.91120298380677,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4H",
			"roundness": null,
			"seed": 1193944031,
			"version": 250,
			"versionNonce": 37926865,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.8154519440157846
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					11.262022581277451
				],
				[
					0,
					14.077474525293237
				],
				[
					0,
					19.708378413324805
				],
				[
					0,
					25.339497106570686
				],
				[
					0,
					28.154949050586474
				],
				[
					0,
					33.78585293861804
				],
				[
					0,
					39.41697163186393
				],
				[
					0,
					42.232423575879714
				],
				[
					0,
					47.86332746391128
				],
				[
					0,
					50.67877940792706
				],
				[
					0,
					53.49444615715716
				],
				[
					0,
					56.30989810117295
				],
				[
					0,
					59.125350045188725
				],
				[
					0,
					61.94080198920451
				],
				[
					5.630903888031569,
					61.94080198920451
				],
				[
					8.446570637261669,
					61.94080198920451
				],
				[
					11.261807776063138,
					61.94080198920451
				],
				[
					14.077474525293237,
					61.94080198920451
				],
				[
					16.893141274523337,
					61.94080198920451
				],
				[
					16.893141274523337,
					59.125350045188725
				],
				[
					19.708378413324805,
					59.125350045188725
				],
				[
					22.524045162554902,
					56.30989810117295
				],
				[
					25.339282301356377,
					53.49444615715716
				],
				[
					28.154949050586474,
					53.49444615715716
				],
				[
					28.154949050586474,
					50.67877940792706
				],
				[
					30.97061579981657,
					50.67877940792706
				],
				[
					30.97061579981657,
					47.86332746391128
				],
				[
					30.97061579981657,
					45.0478755198955
				],
				[
					33.78585293861804,
					45.0478755198955
				],
				[
					36.60151968784814,
					42.232423575879714
				],
				[
					39.41675682664961,
					30.970400994602254
				],
				[
					39.41675682664961,
					25.339497106570686
				],
				[
					39.41675682664961,
					19.708378413324805
				],
				[
					42.232423575879714,
					16.89292646930902
				],
				[
					45.048090325109804,
					11.262022581277451
				],
				[
					45.048090325109804,
					8.446355832047352
				],
				[
					45.048090325109804,
					5.630903888031569
				],
				[
					45.048090325109804,
					2.8154519440157846
				],
				[
					45.048090325109804,
					-2.8154519440157846
				],
				[
					47.86332746391128,
					-5.631118693245884
				],
				[
					47.86332746391128,
					-11.262022581277451
				],
				[
					47.86332746391128,
					-14.077474525293237
				],
				[
					47.86332746391128,
					-16.89292646930902
				],
				[
					47.86332746391128,
					-14.077474525293237
				],
				[
					47.86332746391128,
					-8.446570637261669
				],
				[
					47.86332746391128,
					-2.8154519440157846
				],
				[
					47.86332746391128,
					2.8154519440157846
				],
				[
					47.86332746391128,
					11.262022581277451
				],
				[
					47.86332746391128,
					16.89292646930902
				],
				[
					47.86332746391128,
					22.52383035734059
				],
				[
					47.86332746391128,
					28.154949050586474
				],
				[
					47.86332746391128,
					33.78585293861804
				],
				[
					47.86332746391128,
					36.601304882633826
				],
				[
					47.86332746391128,
					42.232423575879714
				],
				[
					47.86332746391128,
					47.86332746391128
				],
				[
					47.86332746391128,
					50.67877940792706
				],
				[
					47.86332746391128,
					53.49444615715716
				],
				[
					47.86332746391128,
					56.30989810117295
				],
				[
					47.86332746391128,
					59.125350045188725
				],
				[
					47.86332746391128,
					61.94080198920451
				],
				[
					47.86332746391128,
					67.5719206824504
				],
				[
					47.86332746391128,
					70.38737262646619
				],
				[
					47.86332746391128,
					73.20282457048197
				],
				[
					47.86332746391128,
					76.01827651449776
				],
				[
					50.67899421314137,
					76.01827651449776
				],
				[
					50.67899421314137,
					73.20282457048197
				],
				[
					50.67899421314137,
					64.7562539332203
				],
				[
					50.67899421314137,
					61.94080198920451
				],
				[
					50.67899421314137,
					61.94080198920451
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "xlnfwbgn88iCyyrQ-hpLn",
			"type": "freedraw",
			"x": 6074.273469252496,
			"y": -720.798381207562,
			"width": 78.83394326372786,
			"height": 8.446570637261669,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4I",
			"roundness": null,
			"seed": 1058557951,
			"version": 199,
			"versionNonce": 429757873,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8152371388014705,
					0
				],
				[
					8.446570637261669,
					0
				],
				[
					11.26180777606314,
					2.815451944015785
				],
				[
					16.89271166409471,
					2.815451944015785
				],
				[
					25.339282301356377,
					8.446570637261669
				],
				[
					33.78585293861805,
					8.446570637261669
				],
				[
					39.41675682664962,
					8.446570637261669
				],
				[
					45.047660714681186,
					8.446570637261669
				],
				[
					47.86332746391128,
					8.446570637261669
				],
				[
					50.67899421314138,
					8.446570637261669
				],
				[
					53.49423135194286,
					8.446570637261669
				],
				[
					56.30989810117295,
					8.446570637261669
				],
				[
					59.12513523997442,
					8.446570637261669
				],
				[
					61.94080198920452,
					8.446570637261669
				],
				[
					64.75646873843462,
					8.446570637261669
				],
				[
					67.5717058772361,
					5.63090388803157
				],
				[
					70.38737262646619,
					2.815451944015785
				],
				[
					73.20260976526767,
					2.815451944015785
				],
				[
					78.83394326372786,
					2.815451944015785
				],
				[
					78.83394326372786,
					2.815451944015785
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "1-mOGu5mKruO16ePv04mM",
			"type": "freedraw",
			"x": 6170.0001241803175,
			"y": -726.4292850955933,
			"width": 42.232423575879714,
			"height": 129.5127226716549,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4J",
			"roundness": null,
			"seed": 1286338591,
			"version": 216,
			"versionNonce": 564246417,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8156667492300986,
					-2.815666749230098
				],
				[
					5.630903888031569,
					-5.631118693245883
				],
				[
					14.077474525293237,
					-14.077474525293235
				],
				[
					19.708378413324805,
					-22.5240451625549
				],
				[
					28.154949050586474,
					-30.970615799816567
				],
				[
					33.78585293861804,
					-39.41697163186392
				],
				[
					36.60151968784814,
					-45.0480903251098
				],
				[
					39.41718643707824,
					-50.678994213141365
				],
				[
					39.41718643707824,
					-53.49444615715715
				],
				[
					39.41718643707824,
					-56.30989810117294
				],
				[
					42.232423575879714,
					-59.12556485040303
				],
				[
					42.232423575879714,
					-61.94101679441882
				],
				[
					42.232423575879714,
					-59.12556485040303
				],
				[
					42.232423575879714,
					-56.30989810117294
				],
				[
					42.232423575879714,
					-50.678994213141365
				],
				[
					42.232423575879714,
					-45.0480903251098
				],
				[
					42.232423575879714,
					-39.41697163186392
				],
				[
					42.232423575879714,
					-36.60151968784813
				],
				[
					42.232423575879714,
					-28.15494905058647
				],
				[
					39.41718643707824,
					-19.708593218539118
				],
				[
					39.41718643707824,
					-11.26202258127745
				],
				[
					39.41718643707824,
					-2.815666749230098
				],
				[
					36.60151968784814,
					2.815451944015784
				],
				[
					36.60151968784814,
					11.261807776063137
				],
				[
					36.60151968784814,
					19.7083784133248
				],
				[
					36.60151968784814,
					25.339282301356373
				],
				[
					36.60151968784814,
					28.15494905058647
				],
				[
					36.60151968784814,
					33.785852938618035
				],
				[
					36.60151968784814,
					39.4167568266496
				],
				[
					36.60151968784814,
					45.04787551989549
				],
				[
					36.60151968784814,
					50.67877940792705
				],
				[
					33.78585293861804,
					56.30989810117294
				],
				[
					33.78585293861804,
					59.12535004518872
				],
				[
					33.78585293861804,
					61.9408019892045
				],
				[
					33.78585293861804,
					64.75625393322028
				],
				[
					30.97061579981657,
					67.57170587723607
				],
				[
					30.97061579981657,
					67.57170587723607
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "lc4KBhbFfcr6v1bNVzZbx",
			"type": "freedraw",
			"x": 6181.262361566808,
			"y": -658.8575792183576,
			"width": 56.30989810117295,
			"height": 2.8156667492300986,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4K",
			"roundness": null,
			"seed": 366320703,
			"version": 195,
			"versionNonce": 1015455089,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.815666749230099,
					0
				],
				[
					0,
					0
				],
				[
					2.8152371388014705,
					0
				],
				[
					11.261807776063138,
					0
				],
				[
					16.89271166409471,
					0
				],
				[
					22.523615552126277,
					2.8156667492300986
				],
				[
					28.154949050586477,
					2.8156667492300986
				],
				[
					33.78585293861804,
					2.8156667492300986
				],
				[
					36.601090077419514,
					2.8156667492300986
				],
				[
					39.41675682664962,
					2.8156667492300986
				],
				[
					42.23242357587972,
					2.8156667492300986
				],
				[
					45.047660714681186,
					2.8156667492300986
				],
				[
					47.86332746391129,
					2.8156667492300986
				],
				[
					50.67856460271276,
					2.8156667492300986
				],
				[
					53.49423135194285,
					2.8156667492300986
				],
				[
					53.49423135194285,
					2.8156667492300986
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "1yERErb0yaOqB8_xCt2eR",
			"type": "arrow",
			"x": 5257.779731980271,
			"y": -402.64747841645635,
			"width": 0,
			"height": 399.8002979988494,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4L",
			"roundness": {
				"type": 2
			},
			"seed": 779467871,
			"version": 214,
			"versionNonce": 1502857041,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					399.8002979988494
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "487DOrcQVNhxImY7BVooJ",
			"type": "freedraw",
			"x": 4731.28227065639,
			"y": 202.68403357375973,
			"width": 121.06636683960755,
			"height": 180.1917168847963,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4M",
			"roundness": null,
			"seed": 1516034175,
			"version": 217,
			"versionNonce": 320910641,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.815666749230099
				],
				[
					2.8154519440157846,
					-14.077474525293239
				],
				[
					8.446570637261667,
					-30.970615799816574
				],
				[
					14.077474525293235,
					-47.863542269125595
				],
				[
					19.708378413324805,
					-59.125564850403045
				],
				[
					25.339497106570686,
					-73.20303937569629
				],
				[
					30.97040099460226,
					-84.46484715175944
				],
				[
					36.60151968784814,
					-98.54232167705267
				],
				[
					45.0478755198955,
					-112.61979620234591
				],
				[
					50.67899421314137,
					-123.88181878362334
				],
				[
					59.12535004518873,
					-137.95929330891659
				],
				[
					61.94080198920452,
					-146.40586394617827
				],
				[
					64.75646873843462,
					-152.03676783420983
				],
				[
					70.38737262646617,
					-157.66788652745575
				],
				[
					73.20282457048197,
					-163.2987904154873
				],
				[
					76.01827651449776,
					-166.1142423595031
				],
				[
					78.83394326372785,
					-171.74536105274896
				],
				[
					78.83394326372785,
					-174.56081299676475
				],
				[
					81.64939520774364,
					-177.37626494078054
				],
				[
					81.64939520774364,
					-180.1917168847963
				],
				[
					84.46484715175943,
					-174.56081299676475
				],
				[
					87.2802990957752,
					-168.9296943035189
				],
				[
					90.095751039791,
					-160.4833384714715
				],
				[
					95.72686973303686,
					-152.03676783420983
				],
				[
					98.54232167705266,
					-137.95929330891659
				],
				[
					101.35777362106843,
					-129.51293747686924
				],
				[
					106.98889231431433,
					-118.25091489559179
				],
				[
					109.80434425833012,
					-106.98889231431433
				],
				[
					112.61979620234588,
					-95.72686973303688
				],
				[
					115.43524814636167,
					-84.46484715175944
				],
				[
					115.43524814636167,
					-76.01849131971208
				],
				[
					115.43524814636167,
					-67.5719206824504
				],
				[
					118.25070009037746,
					-61.941016794418836
				],
				[
					118.25070009037746,
					-59.125564850403045
				],
				[
					118.25070009037746,
					-56.309898101172955
				],
				[
					121.06636683960755,
					-56.309898101172955
				],
				[
					121.06636683960755,
					-53.494446157157164
				],
				[
					121.06636683960755,
					-50.67899421314138
				],
				[
					121.06636683960755,
					-50.67899421314138
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "zUJfjFe9kejcZkVmwKxj1",
			"type": "freedraw",
			"x": 4776.330146176286,
			"y": 115.40351967277047,
			"width": 78.83394326372786,
			"height": 8.446355832047352,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4N",
			"roundness": null,
			"seed": 256602271,
			"version": 198,
			"versionNonce": 1284826897,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.815451944015785,
					-2.8154519440157837
				],
				[
					8.446570637261669,
					-2.8154519440157837
				],
				[
					11.262022581277453,
					-2.8154519440157837
				],
				[
					16.892926469309025,
					-5.630903888031567
				],
				[
					22.524045162554906,
					-5.630903888031567
				],
				[
					28.154949050586474,
					-5.630903888031567
				],
				[
					33.78606774383236,
					-5.630903888031567
				],
				[
					36.601519687848146,
					-5.630903888031567
				],
				[
					45.047875519895506,
					-5.630903888031567
				],
				[
					47.863542269125595,
					-5.630903888031567
				],
				[
					50.67899421314138,
					-5.630903888031567
				],
				[
					56.30989810117295,
					-5.630903888031567
				],
				[
					61.941016794418836,
					-5.630903888031567
				],
				[
					64.75646873843462,
					-5.630903888031567
				],
				[
					70.38737262646619,
					-5.630903888031567
				],
				[
					73.20282457048198,
					-5.630903888031567
				],
				[
					76.01849131971208,
					-5.630903888031567
				],
				[
					78.83394326372786,
					-5.630903888031567
				],
				[
					78.83394326372786,
					-8.446355832047352
				],
				[
					78.83394326372786,
					-8.446355832047352
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "86jEM-WdXKtKBfttntgIR",
			"type": "freedraw",
			"x": 4905.842868847941,
			"y": 143.55846872335678,
			"width": 50.67899421314137,
			"height": 78.83372845851353,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4O",
			"roundness": null,
			"seed": 921830591,
			"version": 242,
			"versionNonce": 275242225,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.815451944015784,
					-2.8154519440157846
				],
				[
					-5.630903888031568,
					-2.8154519440157846
				],
				[
					-5.630903888031568,
					-5.630903888031569
				],
				[
					-8.446355832047352,
					-5.630903888031569
				],
				[
					-14.077474525293235,
					-8.446355832047352
				],
				[
					-16.89292646930902,
					-8.446355832047352
				],
				[
					-19.7083784133248,
					-8.446355832047352
				],
				[
					-25.339282301356373,
					-8.446355832047352
				],
				[
					-28.15494905058647,
					-5.630903888031569
				],
				[
					-30.970400994602254,
					-2.8154519440157846
				],
				[
					-33.78585293861804,
					0
				],
				[
					-39.4167568266496,
					2.8156667492300986
				],
				[
					-42.23242357587971,
					5.631118693245884
				],
				[
					-42.23242357587971,
					11.262022581277453
				],
				[
					-45.04787551989549,
					14.077474525293237
				],
				[
					-45.04787551989549,
					16.893141274523337
				],
				[
					-45.04787551989549,
					19.70859321853912
				],
				[
					-45.04787551989549,
					22.524045162554906
				],
				[
					-45.04787551989549,
					25.339497106570686
				],
				[
					-45.04787551989549,
					28.154949050586474
				],
				[
					-45.04787551989549,
					30.970615799816574
				],
				[
					-45.04787551989549,
					33.786067743832355
				],
				[
					-45.04787551989549,
					36.60151968784814
				],
				[
					-45.04787551989549,
					39.41697163186393
				],
				[
					-45.04787551989549,
					45.04809032510981
				],
				[
					-45.04787551989549,
					50.67899421314137
				],
				[
					-45.04787551989549,
					53.49444615715716
				],
				[
					-42.23242357587971,
					53.49444615715716
				],
				[
					-42.23242357587971,
					56.30989810117295
				],
				[
					-39.4167568266496,
					56.30989810117295
				],
				[
					-39.4167568266496,
					59.125564850403045
				],
				[
					-36.60130488263382,
					59.125564850403045
				],
				[
					-30.970400994602254,
					61.941016794418836
				],
				[
					-30.970400994602254,
					64.75646873843462
				],
				[
					-25.339282301356373,
					64.75646873843462
				],
				[
					-22.523830357340586,
					67.5719206824504
				],
				[
					-19.7083784133248,
					70.38737262646619
				],
				[
					-16.89292646930902,
					70.38737262646619
				],
				[
					-14.077474525293235,
					70.38737262646619
				],
				[
					-11.261807776063137,
					70.38737262646619
				],
				[
					-8.446355832047352,
					70.38737262646619
				],
				[
					-2.815451944015784,
					70.38737262646619
				],
				[
					-2.815451944015784,
					67.5719206824504
				],
				[
					0,
					67.5719206824504
				],
				[
					0,
					64.75646873843462
				],
				[
					2.815666749230098,
					61.941016794418836
				],
				[
					2.815666749230098,
					59.125564850403045
				],
				[
					5.631118693245883,
					59.125564850403045
				],
				[
					5.631118693245883,
					56.30989810117295
				],
				[
					5.631118693245883,
					53.49444615715716
				],
				[
					5.631118693245883,
					47.86354226912559
				],
				[
					5.631118693245883,
					45.04809032510981
				],
				[
					5.631118693245883,
					42.232423575879714
				],
				[
					5.631118693245883,
					39.41697163186393
				],
				[
					5.631118693245883,
					45.04809032510981
				],
				[
					5.631118693245883,
					50.67899421314137
				],
				[
					5.631118693245883,
					53.49444615715716
				],
				[
					5.631118693245883,
					56.30989810117295
				],
				[
					5.631118693245883,
					59.125564850403045
				],
				[
					5.631118693245883,
					64.75646873843462
				],
				[
					5.631118693245883,
					67.5719206824504
				],
				[
					5.631118693245883,
					67.5719206824504
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "LPd9t2iSVv25vfKmzPg8w",
			"type": "freedraw",
			"x": 4897.396513015893,
			"y": 177.34453646718907,
			"width": 42.232423575879714,
			"height": 2.8154519440157846,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4P",
			"roundness": null,
			"seed": 821105887,
			"version": 187,
			"versionNonce": 773920465,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.630903888031569,
					0
				],
				[
					8.446355832047352,
					0
				],
				[
					14.077474525293237,
					0
				],
				[
					22.52383035734059,
					0
				],
				[
					30.970400994602254,
					0
				],
				[
					36.601304882633826,
					2.8154519440157846
				],
				[
					39.41697163186393,
					2.8154519440157846
				],
				[
					42.232423575879714,
					2.8154519440157846
				],
				[
					42.232423575879714,
					2.8154519440157846
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "s8TKjqNdsydwait9Grs9F",
			"type": "freedraw",
			"x": 4950.89095917305,
			"y": 121.03463836601622,
			"width": 53.494231351942844,
			"height": 101.35777362106843,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4Q",
			"roundness": null,
			"seed": 349774079,
			"version": 223,
			"versionNonce": 408425649,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					8.446355832047352
				],
				[
					0,
					11.262022581277451
				],
				[
					0,
					16.89292646930902
				],
				[
					0,
					22.52383035734059
				],
				[
					0,
					25.339497106570686
				],
				[
					0,
					30.970400994602254
				],
				[
					0,
					33.78585293861804
				],
				[
					0,
					39.41697163186393
				],
				[
					0,
					42.232423575879714
				],
				[
					0,
					45.0478755198955
				],
				[
					0,
					47.86332746391128
				],
				[
					0,
					50.67877940792706
				],
				[
					0,
					53.49444615715716
				],
				[
					0,
					56.30989810117295
				],
				[
					0,
					59.125350045188725
				],
				[
					0,
					61.94080198920451
				],
				[
					0,
					64.7562539332203
				],
				[
					0,
					67.5719206824504
				],
				[
					0,
					70.38737262646619
				],
				[
					0,
					73.20282457048197
				],
				[
					0,
					76.01827651449776
				],
				[
					2.8154519440157846,
					76.01827651449776
				],
				[
					2.8154519440157846,
					78.83372845851353
				],
				[
					5.630903888031569,
					81.64939520774364
				],
				[
					8.446355832047352,
					84.46484715175943
				],
				[
					8.446355832047352,
					87.2802990957752
				],
				[
					11.261807776063138,
					90.095751039791
				],
				[
					14.077474525293237,
					92.91120298380677
				],
				[
					14.077474525293237,
					95.72686973303686
				],
				[
					16.89292646930902,
					95.72686973303686
				],
				[
					19.708378413324805,
					95.72686973303686
				],
				[
					22.52383035734059,
					98.54232167705266
				],
				[
					25.339282301356377,
					101.35777362106843
				],
				[
					28.154949050586474,
					101.35777362106843
				],
				[
					30.970400994602254,
					101.35777362106843
				],
				[
					33.78585293861804,
					101.35777362106843
				],
				[
					36.601304882633826,
					101.35777362106843
				],
				[
					39.41675682664961,
					101.35777362106843
				],
				[
					42.232423575879714,
					101.35777362106843
				],
				[
					47.86332746391128,
					101.35777362106843
				],
				[
					50.67877940792706,
					98.54232167705266
				],
				[
					53.494231351942844,
					98.54232167705266
				],
				[
					53.494231351942844,
					95.72686973303686
				],
				[
					53.494231351942844,
					95.72686973303686
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "DYtCGdIncby0ufHbsjpOw",
			"type": "freedraw",
			"x": 5007.200857274223,
			"y": 135.11211289130938,
			"width": 50.67877940792706,
			"height": 115.43524814636169,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4R",
			"roundness": null,
			"seed": 875211039,
			"version": 247,
			"versionNonce": 45373073,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.63090388803157
				],
				[
					0,
					8.446355832047354
				],
				[
					0,
					11.262022581277453
				],
				[
					0,
					16.892926469309025
				],
				[
					0,
					22.523830357340593
				],
				[
					0,
					28.154949050586474
				],
				[
					0,
					33.78585293861805
				],
				[
					0,
					39.41697163186393
				],
				[
					0,
					45.047875519895506
				],
				[
					0,
					47.86332746391128
				],
				[
					0,
					50.67877940792707
				],
				[
					0,
					53.49444615715717
				],
				[
					0,
					56.30989810117295
				],
				[
					0,
					59.12535004518873
				],
				[
					0,
					61.94080198920452
				],
				[
					0,
					64.75625393322031
				],
				[
					0,
					67.57192068245041
				],
				[
					2.8154519440157846,
					70.38737262646619
				],
				[
					5.630903888031569,
					73.20282457048198
				],
				[
					8.446355832047352,
					78.83372845851355
				],
				[
					8.446355832047352,
					81.64939520774365
				],
				[
					11.261807776063138,
					81.64939520774365
				],
				[
					14.077474525293237,
					81.64939520774365
				],
				[
					16.89292646930902,
					81.64939520774365
				],
				[
					19.708378413324805,
					81.64939520774365
				],
				[
					22.52383035734059,
					81.64939520774365
				],
				[
					25.339282301356377,
					81.64939520774365
				],
				[
					28.154949050586474,
					81.64939520774365
				],
				[
					28.154949050586474,
					78.83372845851355
				],
				[
					30.970400994602254,
					78.83372845851355
				],
				[
					33.78585293861804,
					76.01827651449777
				],
				[
					33.78585293861804,
					73.20282457048198
				],
				[
					36.601304882633826,
					70.38737262646619
				],
				[
					39.41675682664961,
					67.57192068245041
				],
				[
					42.232423575879714,
					64.75625393322031
				],
				[
					42.232423575879714,
					59.12535004518873
				],
				[
					45.0478755198955,
					53.49444615715717
				],
				[
					45.0478755198955,
					50.67877940792707
				],
				[
					47.86332746391128,
					45.047875519895506
				],
				[
					47.86332746391128,
					42.23242357587972
				],
				[
					50.67877940792706,
					30.97040099460226
				],
				[
					50.67877940792706,
					28.154949050586474
				],
				[
					50.67877940792706,
					25.33949710657069
				],
				[
					50.67877940792706,
					22.523830357340593
				],
				[
					50.67877940792706,
					19.70837841332481
				],
				[
					50.67877940792706,
					16.892926469309025
				],
				[
					50.67877940792706,
					14.077474525293237
				],
				[
					50.67877940792706,
					11.262022581277453
				],
				[
					50.67877940792706,
					8.446355832047354
				],
				[
					50.67877940792706,
					5.63090388803157
				],
				[
					50.67877940792706,
					8.446355832047354
				],
				[
					50.67877940792706,
					14.077474525293237
				],
				[
					50.67877940792706,
					25.33949710657069
				],
				[
					50.67877940792706,
					33.78585293861805
				],
				[
					50.67877940792706,
					42.23242357587972
				],
				[
					50.67877940792706,
					53.49444615715717
				],
				[
					50.67877940792706,
					61.94080198920452
				],
				[
					50.67877940792706,
					73.20282457048198
				],
				[
					50.67877940792706,
					81.64939520774365
				],
				[
					47.86332746391128,
					95.72686973303688
				],
				[
					47.86332746391128,
					104.17322556508422
				],
				[
					47.86332746391128,
					109.80434425833013
				],
				[
					47.86332746391128,
					112.6197962023459
				],
				[
					47.86332746391128,
					115.43524814636169
				],
				[
					47.86332746391128,
					112.6197962023459
				],
				[
					50.67877940792706,
					106.98867750910001
				],
				[
					50.67877940792706,
					104.17322556508422
				],
				[
					50.67877940792706,
					101.35777362106845
				],
				[
					50.67877940792706,
					101.35777362106845
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "-mEIO9mkhY_ulwI7VRSsb",
			"type": "freedraw",
			"x": 5139.529031889893,
			"y": 143.55846872335678,
			"width": 36.601304882633826,
			"height": 42.232423575879714,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4S",
			"roundness": null,
			"seed": 1549151551,
			"version": 200,
			"versionNonce": 1072520305,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8154519440157846,
					0
				],
				[
					11.262022581277451,
					-2.8154519440157846
				],
				[
					14.077474525293237,
					-2.8154519440157846
				],
				[
					22.524045162554902,
					-5.630903888031569
				],
				[
					25.339497106570686,
					-8.446355832047354
				],
				[
					28.154949050586474,
					-11.261807776063138
				],
				[
					30.970400994602254,
					-11.261807776063138
				],
				[
					33.78585293861804,
					-11.261807776063138
				],
				[
					30.970400994602254,
					-11.261807776063138
				],
				[
					30.970400994602254,
					-8.446355832047354
				],
				[
					28.154949050586474,
					-5.630903888031569
				],
				[
					25.339497106570686,
					0
				],
				[
					19.708378413324805,
					5.631118693245884
				],
				[
					16.89292646930902,
					8.44657063726167
				],
				[
					11.262022581277451,
					14.077474525293239
				],
				[
					5.630903888031569,
					19.708593218539125
				],
				[
					2.8154519440157846,
					22.524045162554906
				],
				[
					0,
					25.33949710657069
				],
				[
					-2.8154519440157846,
					28.154949050586477
				],
				[
					-2.8154519440157846,
					30.970615799816574
				],
				[
					-2.8154519440157846,
					30.970615799816574
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "wqwl2nJnrj0pgqc50KPkH",
			"type": "freedraw",
			"x": 5139.529031889893,
			"y": 174.5290845231732,
			"width": 50.67899421314137,
			"height": 14.077474525293237,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4T",
			"roundness": null,
			"seed": 1488727391,
			"version": 193,
			"versionNonce": 1607116369,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.630903888031569,
					0
				],
				[
					8.446570637261669,
					0
				],
				[
					14.077474525293237,
					-2.8156667492300986
				],
				[
					19.708378413324805,
					-5.631118693245884
				],
				[
					22.524045162554902,
					-5.631118693245884
				],
				[
					25.339497106570686,
					-5.631118693245884
				],
				[
					28.154949050586474,
					-5.631118693245884
				],
				[
					33.78585293861804,
					-5.631118693245884
				],
				[
					33.78585293861804,
					-8.446570637261669
				],
				[
					42.232423575879714,
					-8.446570637261669
				],
				[
					42.232423575879714,
					-11.262022581277451
				],
				[
					47.86332746391128,
					-11.262022581277451
				],
				[
					47.86332746391128,
					-14.077474525293237
				],
				[
					50.67899421314137,
					-14.077474525293237
				],
				[
					50.67899421314137,
					-14.077474525293237
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "SggmUDGZsywx4uwi91YbI",
			"type": "freedraw",
			"x": 5361.95317235057,
			"y": 11.230294107686177,
			"width": 14.077474525293237,
			"height": 202.71554724213686,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4U",
			"roundness": null,
			"seed": 883763583,
			"version": 199,
			"versionNonce": 220443697,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157846
				],
				[
					0,
					0
				],
				[
					0,
					8.446570637261669
				],
				[
					0,
					22.524045162554902
				],
				[
					-2.8154519440157846,
					47.86332746391128
				],
				[
					-5.631118693245884,
					70.38737262646619
				],
				[
					-8.446570637261669,
					92.91141778902109
				],
				[
					-8.446570637261669,
					118.25070009037745
				],
				[
					-8.446570637261669,
					137.95929330891659
				],
				[
					-8.446570637261669,
					157.66767172224138
				],
				[
					-8.446570637261669,
					171.74514624753462
				],
				[
					-8.446570637261669,
					185.8226207728279
				],
				[
					-8.446570637261669,
					194.26919141008952
				],
				[
					-8.446570637261669,
					197.0846433541053
				],
				[
					-8.446570637261669,
					199.90009529812107
				],
				[
					-11.262022581277451,
					199.90009529812107
				],
				[
					-11.262022581277451,
					197.0846433541053
				],
				[
					-14.077474525293237,
					194.26919141008952
				],
				[
					-14.077474525293237,
					191.45373946607373
				],
				[
					-14.077474525293237,
					188.63807271684365
				],
				[
					-14.077474525293237,
					188.63807271684365
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "NxjBjCHe4ZhxBoaGKGDCG",
			"type": "freedraw",
			"x": 5359.137720406554,
			"y": 2.78372347042432,
			"width": 59.12556485040304,
			"height": 104.17344037029852,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4V",
			"roundness": null,
			"seed": 1030332831,
			"version": 234,
			"versionNonce": 736101905,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.815451944015784
				],
				[
					2.815451944015784,
					-2.815451944015784
				],
				[
					5.630903888031568,
					-5.630903888031568
				],
				[
					8.446355832047354,
					-5.630903888031568
				],
				[
					14.077474525293235,
					-8.446355832047352
				],
				[
					19.7083784133248,
					-11.261807776063137
				],
				[
					22.52383035734059,
					-11.261807776063137
				],
				[
					25.339282301356377,
					-11.261807776063137
				],
				[
					28.15494905058647,
					-14.077474525293233
				],
				[
					30.970400994602258,
					-14.077474525293233
				],
				[
					33.78585293861804,
					-16.892926469309018
				],
				[
					36.601304882633826,
					-16.892926469309018
				],
				[
					39.4167568266496,
					-16.892926469309018
				],
				[
					42.232423575879714,
					-16.892926469309018
				],
				[
					45.0478755198955,
					-16.892926469309018
				],
				[
					47.86332746391128,
					-14.077474525293233
				],
				[
					50.67877940792707,
					-14.077474525293233
				],
				[
					50.67877940792707,
					-11.261807776063137
				],
				[
					50.67877940792707,
					-8.446355832047352
				],
				[
					53.494231351942844,
					-8.446355832047352
				],
				[
					53.494231351942844,
					-5.630903888031568
				],
				[
					56.30989810117294,
					-2.815451944015784
				],
				[
					56.30989810117294,
					0
				],
				[
					56.30989810117294,
					5.631118693245883
				],
				[
					56.30989810117294,
					11.262022581277451
				],
				[
					56.30989810117294,
					14.077474525293233
				],
				[
					56.30989810117294,
					19.708593218539118
				],
				[
					56.30989810117294,
					22.524045162554902
				],
				[
					56.30989810117294,
					25.339497106570683
				],
				[
					56.30989810117294,
					33.786067743832355
				],
				[
					56.30989810117294,
					36.60151968784814
				],
				[
					53.494231351942844,
					39.41697163186392
				],
				[
					53.494231351942844,
					42.23242357587971
				],
				[
					53.494231351942844,
					45.048090325109804
				],
				[
					50.67877940792707,
					47.86354226912558
				],
				[
					47.86332746391128,
					53.49444615715716
				],
				[
					45.0478755198955,
					53.49444615715716
				],
				[
					45.0478755198955,
					56.309898101172934
				],
				[
					42.232423575879714,
					59.12556485040304
				],
				[
					39.4167568266496,
					61.941016794418815
				],
				[
					39.4167568266496,
					64.7564687384346
				],
				[
					36.601304882633826,
					64.7564687384346
				],
				[
					33.78585293861804,
					67.57192068245038
				],
				[
					30.970400994602258,
					67.57192068245038
				],
				[
					25.339282301356377,
					70.38737262646617
				],
				[
					25.339282301356377,
					73.20303937569628
				],
				[
					19.7083784133248,
					76.01849131971206
				],
				[
					16.89292646930902,
					78.83394326372785
				],
				[
					11.261807776063137,
					81.64939520774362
				],
				[
					8.446355832047354,
					81.64939520774362
				],
				[
					2.815451944015784,
					84.46484715175941
				],
				[
					2.815451944015784,
					87.2805139009895
				],
				[
					0,
					87.2805139009895
				],
				[
					-2.8156667492300986,
					87.2805139009895
				],
				[
					-2.8156667492300986,
					87.2805139009895
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "9dEXsK7ev2ZTzopJwY07r",
			"type": "freedraw",
			"x": 5333.798223299983,
			"y": 208.3149374617915,
			"width": 67.5719206824504,
			"height": 11.262022581277451,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4W",
			"roundness": null,
			"seed": 1143084479,
			"version": 191,
			"versionNonce": 922164209,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508774,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.630903888031569,
					0
				],
				[
					11.262022581277451,
					0
				],
				[
					19.708378413324805,
					-2.815451944015784
				],
				[
					30.970400994602254,
					-2.815451944015784
				],
				[
					39.41697163186393,
					-5.630903888031568
				],
				[
					47.86332746391128,
					-8.446570637261667
				],
				[
					53.49444615715716,
					-8.446570637261667
				],
				[
					59.125350045188725,
					-8.446570637261667
				],
				[
					61.94080198920451,
					-8.446570637261667
				],
				[
					64.7562539332203,
					-8.446570637261667
				],
				[
					67.5719206824504,
					-8.446570637261667
				],
				[
					67.5719206824504,
					-11.262022581277451
				],
				[
					67.5719206824504,
					-11.262022581277451
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "wvUH0MILzjMMoX6rHTKan",
			"type": "freedraw",
			"x": 5727.967510008195,
			"y": 182.9754403552206,
			"width": 101.35798842628274,
			"height": 211.16211787939855,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4X",
			"roundness": null,
			"seed": 536282591,
			"version": 219,
			"versionNonce": 1584428497,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-5.630903888031569
				],
				[
					0,
					-11.262022581277451
				],
				[
					0,
					-19.708378413324805
				],
				[
					2.8156667492300986,
					-42.232423575879714
				],
				[
					5.630903888031569,
					-59.125350045188725
				],
				[
					8.446570637261669,
					-78.83372845851353
				],
				[
					14.077474525293237,
					-95.72686973303686
				],
				[
					16.893141274523337,
					-115.43524814636169
				],
				[
					19.708378413324805,
					-129.5127226716549
				],
				[
					22.524045162554902,
					-146.40564914096393
				],
				[
					28.154949050586474,
					-160.48312366625717
				],
				[
					28.154949050586474,
					-171.74514624753462
				],
				[
					33.78585293861804,
					-177.3760501355662
				],
				[
					33.78585293861804,
					-180.1917168847963
				],
				[
					33.78585293861804,
					-185.8226207728279
				],
				[
					36.60151968784814,
					-191.45352466085944
				],
				[
					36.60151968784814,
					-194.26919141008952
				],
				[
					39.41675682664961,
					-199.90009529812107
				],
				[
					42.232423575879714,
					-202.71554724213686
				],
				[
					42.232423575879714,
					-205.53099918615266
				],
				[
					42.232423575879714,
					-208.34666593538276
				],
				[
					42.232423575879714,
					-211.16211787939855
				],
				[
					45.048090325109804,
					-208.34666593538276
				],
				[
					47.86332746391128,
					-202.71554724213686
				],
				[
					56.30989810117295,
					-183.0071688288121
				],
				[
					61.94080198920451,
					-166.11424235950307
				],
				[
					70.38737262646619,
					-143.59019719694814
				],
				[
					78.83394326372786,
					-123.88181878362333
				],
				[
					81.64918040252932,
					-109.8043442583301
				],
				[
					90.095751039791,
					-92.91120298380677
				],
				[
					90.095751039791,
					-81.64939520774364
				],
				[
					95.72665492782257,
					-73.20282457048197
				],
				[
					98.54232167705266,
					-61.94080198920451
				],
				[
					98.54232167705266,
					-59.125350045188725
				],
				[
					98.54232167705266,
					-53.49444615715716
				],
				[
					98.54232167705266,
					-50.67877940792706
				],
				[
					98.54232167705266,
					-47.86332746391128
				],
				[
					98.54232167705266,
					-45.0478755198955
				],
				[
					101.35798842628274,
					-45.0478755198955
				],
				[
					101.35798842628274,
					-42.232423575879714
				],
				[
					101.35798842628274,
					-42.232423575879714
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "tXVW9DG-T8XFh9CfSRviR",
			"type": "freedraw",
			"x": 5727.967510008195,
			"y": 90.06423737141381,
			"width": 78.83394326372786,
			"height": 14.077474525293237,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4Y",
			"roundness": null,
			"seed": 1878585855,
			"version": 204,
			"versionNonce": 1701024689,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.815666749230099,
					0
				],
				[
					5.63090388803157,
					0
				],
				[
					8.446570637261669,
					-2.8156667492300986
				],
				[
					11.26180777606314,
					-2.8156667492300986
				],
				[
					14.077474525293237,
					-5.631118693245884
				],
				[
					16.893141274523337,
					-5.631118693245884
				],
				[
					19.70837841332481,
					-5.631118693245884
				],
				[
					22.524045162554906,
					-8.446570637261669
				],
				[
					28.154949050586474,
					-8.446570637261669
				],
				[
					30.970615799816578,
					-8.446570637261669
				],
				[
					30.970615799816578,
					-11.262022581277451
				],
				[
					33.78585293861805,
					-11.262022581277451
				],
				[
					36.601519687848146,
					-11.262022581277451
				],
				[
					39.41675682664962,
					-11.262022581277451
				],
				[
					42.23242357587972,
					-11.262022581277451
				],
				[
					42.23242357587972,
					-14.077474525293237
				],
				[
					45.04809032510981,
					-14.077474525293237
				],
				[
					47.86332746391128,
					-14.077474525293237
				],
				[
					50.67899421314138,
					-14.077474525293237
				],
				[
					53.49423135194286,
					-14.077474525293237
				],
				[
					59.125564850403045,
					-14.077474525293237
				],
				[
					64.75646873843462,
					-14.077474525293237
				],
				[
					73.20303937569629,
					-14.077474525293237
				],
				[
					76.01827651449777,
					-14.077474525293237
				],
				[
					78.83394326372786,
					-14.077474525293237
				],
				[
					78.83394326372786,
					-14.077474525293237
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "DJ4HdEVj3XpR5KBq19DTk",
			"type": "freedraw",
			"x": 5910.974678837006,
			"y": 123.85009031003165,
			"width": 53.494231351942844,
			"height": 84.46484715175943,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4Z",
			"roundness": null,
			"seed": 489183775,
			"version": 239,
			"versionNonce": 1073214865,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.8156667492300986,
					0
				],
				[
					-5.630903888031569,
					0
				],
				[
					-5.630903888031569,
					-2.8154519440157846
				],
				[
					-8.446570637261669,
					-2.8154519440157846
				],
				[
					-11.261807776063138,
					-2.8154519440157846
				],
				[
					-14.077474525293237,
					-2.8154519440157846
				],
				[
					-16.893141274523337,
					-2.8154519440157846
				],
				[
					-19.708378413324805,
					0
				],
				[
					-25.339282301356377,
					5.630903888031569
				],
				[
					-30.97061579981657,
					11.262022581277451
				],
				[
					-33.78585293861804,
					14.077474525293237
				],
				[
					-36.60151968784814,
					16.89292646930902
				],
				[
					-39.41675682664961,
					19.708378413324805
				],
				[
					-39.41675682664961,
					22.524045162554902
				],
				[
					-42.232423575879714,
					25.339497106570686
				],
				[
					-45.048090325109804,
					28.154949050586474
				],
				[
					-47.86332746391128,
					33.78585293861804
				],
				[
					-47.86332746391128,
					36.60151968784814
				],
				[
					-50.67899421314137,
					39.41697163186393
				],
				[
					-53.494231351942844,
					42.232423575879714
				],
				[
					-53.494231351942844,
					45.0478755198955
				],
				[
					-53.494231351942844,
					47.86332746391128
				],
				[
					-53.494231351942844,
					50.67899421314137
				],
				[
					-53.494231351942844,
					53.49444615715716
				],
				[
					-53.494231351942844,
					56.30989810117295
				],
				[
					-53.494231351942844,
					59.125350045188725
				],
				[
					-53.494231351942844,
					61.94080198920451
				],
				[
					-53.494231351942844,
					64.75646873843462
				],
				[
					-53.494231351942844,
					67.5719206824504
				],
				[
					-53.494231351942844,
					70.38737262646619
				],
				[
					-53.494231351942844,
					73.20282457048197
				],
				[
					-53.494231351942844,
					76.01827651449776
				],
				[
					-53.494231351942844,
					78.83394326372786
				],
				[
					-53.494231351942844,
					81.64939520774364
				],
				[
					-50.67899421314137,
					81.64939520774364
				],
				[
					-47.86332746391128,
					81.64939520774364
				],
				[
					-45.048090325109804,
					81.64939520774364
				],
				[
					-42.232423575879714,
					81.64939520774364
				],
				[
					-39.41675682664961,
					81.64939520774364
				],
				[
					-36.60151968784814,
					78.83394326372786
				],
				[
					-33.78585293861804,
					78.83394326372786
				],
				[
					-30.97061579981657,
					76.01827651449776
				],
				[
					-30.97061579981657,
					73.20282457048197
				],
				[
					-28.154949050586474,
					73.20282457048197
				],
				[
					-28.154949050586474,
					70.38737262646619
				],
				[
					-25.339282301356377,
					70.38737262646619
				],
				[
					-25.339282301356377,
					67.5719206824504
				],
				[
					-25.339282301356377,
					64.75646873843462
				],
				[
					-22.524045162554902,
					64.75646873843462
				],
				[
					-22.524045162554902,
					61.94080198920451
				],
				[
					-22.524045162554902,
					59.125350045188725
				],
				[
					-22.524045162554902,
					56.30989810117295
				],
				[
					-19.708378413324805,
					56.30989810117295
				],
				[
					-19.708378413324805,
					59.125350045188725
				],
				[
					-16.893141274523337,
					61.94080198920451
				],
				[
					-16.893141274523337,
					67.5719206824504
				],
				[
					-16.893141274523337,
					70.38737262646619
				],
				[
					-16.893141274523337,
					76.01827651449776
				],
				[
					-14.077474525293237,
					78.83394326372786
				],
				[
					-14.077474525293237,
					81.64939520774364
				],
				[
					-14.077474525293237,
					81.64939520774364
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "jCztH7UrQlrICQcrVivUc",
			"type": "freedraw",
			"x": 5863.111351373095,
			"y": 177.34453646718907,
			"width": 42.232423575879714,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4a",
			"roundness": null,
			"seed": 477478463,
			"version": 186,
			"versionNonce": 1902451569,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					11.261807776063138,
					0
				],
				[
					16.892711664094705,
					0
				],
				[
					25.339282301356377,
					0
				],
				[
					33.78585293861804,
					0
				],
				[
					36.60151968784814,
					0
				],
				[
					39.41675682664961,
					0
				],
				[
					42.232423575879714,
					0
				],
				[
					42.232423575879714,
					0
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "jdOQDRB40hdNsH3d6QHB0",
			"type": "freedraw",
			"x": 5978.546384714245,
			"y": 123.85009031003165,
			"width": 11.261807776063138,
			"height": 5.630903888031569,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4b",
			"roundness": null,
			"seed": 1891737183,
			"version": 181,
			"versionNonce": 703759697,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.81523713880147,
					0
				],
				[
					-11.261807776063138,
					5.630903888031569
				],
				[
					-11.261807776063138,
					5.630903888031569
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "B8Ck4uxvKVH7n13-cKuDG",
			"type": "freedraw",
			"x": 5964.468910188952,
			"y": 106.95716384072284,
			"width": 67.57170587723608,
			"height": 112.6197962023459,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4c",
			"roundness": null,
			"seed": 1826388607,
			"version": 202,
			"versionNonce": 620213041,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					8.446355832047352
				],
				[
					0,
					14.077474525293237
				],
				[
					0,
					22.52383035734059
				],
				[
					0,
					30.970400994602254
				],
				[
					-2.81523713880147,
					45.0478755198955
				],
				[
					-5.630903888031569,
					53.49444615715716
				],
				[
					-5.630903888031569,
					67.5719206824504
				],
				[
					-8.44614102683304,
					78.83372845851353
				],
				[
					-8.44614102683304,
					87.2802990957752
				],
				[
					-11.261807776063138,
					95.72686973303686
				],
				[
					-11.261807776063138,
					104.17322556508422
				],
				[
					-11.261807776063138,
					109.8043442583301
				],
				[
					-11.261807776063138,
					112.6197962023459
				],
				[
					0,
					112.6197962023459
				],
				[
					8.446570637261669,
					112.6197962023459
				],
				[
					19.70880802375343,
					112.6197962023459
				],
				[
					28.154949050586474,
					112.6197962023459
				],
				[
					39.41718643707824,
					112.6197962023459
				],
				[
					45.048090325109804,
					112.6197962023459
				],
				[
					50.67899421314137,
					112.6197962023459
				],
				[
					53.49466096237147,
					112.6197962023459
				],
				[
					56.30989810117295,
					112.6197962023459
				],
				[
					56.30989810117295,
					112.6197962023459
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "CwKtrwaV",
			"type": "text",
			"x": 4294.884808542667,
			"y": 402.5840214692737,
			"width": 2275.31982421875,
			"height": 51.382803497841756,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4d",
			"roundness": null,
			"seed": 898028191,
			"version": 393,
			"versionNonce": 1188832529,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"text": "A_GLU is an abundance map where each column is the abundance vector of each pixel in the hyperspectral imaging",
			"rawText": "A_GLU is an abundance map where each column is the abundance vector of each pixel in the hyperspectral imaging",
			"fontSize": 41.106242798273406,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A_GLU is an abundance map where each column is the abundance vector of each pixel in the hyperspectral imaging",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "rpCBibcl26qAhimEGeLE8",
			"type": "arrow",
			"x": 5274.6728732547945,
			"y": 582.77573835407,
			"width": 0,
			"height": 385.7228234735561,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4e",
			"roundness": {
				"type": 2
			},
			"seed": 57747135,
			"version": 242,
			"versionNonce": 2065128177,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					385.7228234735561
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"elbowed": false
		},
		{
			"id": "75DkwNaNzWIsRAkRVXmlX",
			"type": "freedraw",
			"x": 4697.496417717772,
			"y": 1024.808459928799,
			"width": 92.91120298380677,
			"height": 225.2395924046918,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4f",
			"roundness": null,
			"seed": 624686815,
			"version": 269,
			"versionNonce": 1378931921,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157846
				],
				[
					0,
					-5.630903888031569
				],
				[
					-2.8156667492300986,
					-8.44657063726167
				],
				[
					-5.631118693245884,
					-8.44657063726167
				],
				[
					-5.631118693245884,
					-11.262022581277453
				],
				[
					-8.446570637261669,
					-11.262022581277453
				],
				[
					-11.262022581277451,
					-14.077474525293239
				],
				[
					-14.077474525293237,
					-16.89292646930902
				],
				[
					-16.893141274523337,
					-16.89292646930902
				],
				[
					-19.70859321853912,
					-19.70837841332481
				],
				[
					-25.339497106570686,
					-19.70837841332481
				],
				[
					-28.154949050586474,
					-19.70837841332481
				],
				[
					-36.60151968784814,
					-19.70837841332481
				],
				[
					-45.048090325109804,
					-19.70837841332481
				],
				[
					-50.67899421314137,
					-14.077474525293239
				],
				[
					-56.30989810117295,
					-14.077474525293239
				],
				[
					-61.94101679441883,
					-8.44657063726167
				],
				[
					-67.5719206824504,
					-8.44657063726167
				],
				[
					-70.38737262646619,
					-2.8154519440157846
				],
				[
					-70.38737262646619,
					0
				],
				[
					-73.20303937569628,
					2.8154519440157846
				],
				[
					-76.01849131971207,
					5.630903888031569
				],
				[
					-76.01849131971207,
					8.44657063726167
				],
				[
					-78.83394326372786,
					14.077474525293239
				],
				[
					-78.83394326372786,
					16.89292646930902
				],
				[
					-81.64939520774364,
					19.70837841332481
				],
				[
					-81.64939520774364,
					25.33949710657069
				],
				[
					-81.64939520774364,
					30.97040099460226
				],
				[
					-81.64939520774364,
					33.78585293861804
				],
				[
					-81.64939520774364,
					39.41697163186394
				],
				[
					-81.64939520774364,
					42.23242357587972
				],
				[
					-81.64939520774364,
					47.86332746391129
				],
				[
					-81.64939520774364,
					50.67899421314138
				],
				[
					-81.64939520774364,
					53.494446157157164
				],
				[
					-81.64939520774364,
					56.309898101172955
				],
				[
					-78.83394326372786,
					56.309898101172955
				],
				[
					-78.83394326372786,
					59.12535004518873
				],
				[
					-76.01849131971207,
					61.94080198920452
				],
				[
					-73.20303937569628,
					64.75646873843462
				],
				[
					-73.20303937569628,
					67.5719206824504
				],
				[
					-67.5719206824504,
					70.38737262646619
				],
				[
					-64.75646873843462,
					76.01827651449777
				],
				[
					-61.94101679441883,
					78.83394326372787
				],
				[
					-56.30989810117295,
					81.64939520774365
				],
				[
					-47.86354226912559,
					90.09575103979101
				],
				[
					-42.232423575879714,
					95.72686973303688
				],
				[
					-33.786067743832355,
					104.17322556508424
				],
				[
					-28.154949050586474,
					106.98889231431433
				],
				[
					-22.524045162554902,
					109.80434425833012
				],
				[
					-16.893141274523337,
					115.4352481463617
				],
				[
					-11.262022581277451,
					118.25070009037746
				],
				[
					-8.446570637261669,
					121.06636683960758
				],
				[
					-5.631118693245884,
					123.88181878362334
				],
				[
					-2.8156667492300986,
					123.88181878362334
				],
				[
					0,
					126.69727072763914
				],
				[
					2.8154519440157846,
					132.32817461567072
				],
				[
					2.8154519440157846,
					135.1438413649008
				],
				[
					5.630903888031569,
					137.95929330891659
				],
				[
					8.446355832047352,
					137.95929330891659
				],
				[
					8.446355832047352,
					143.59019719694817
				],
				[
					11.261807776063138,
					146.40564914096396
				],
				[
					11.261807776063138,
					149.22131589019406
				],
				[
					11.261807776063138,
					154.85221977822562
				],
				[
					11.261807776063138,
					163.2987904154873
				],
				[
					8.446355832047352,
					171.74514624753465
				],
				[
					5.630903888031569,
					177.37626494078054
				],
				[
					0,
					183.0071688288121
				],
				[
					-2.8156667492300986,
					188.63807271684365
				],
				[
					-8.446570637261669,
					194.26919141008955
				],
				[
					-11.262022581277451,
					199.9000952981211
				],
				[
					-14.077474525293237,
					202.7155472421369
				],
				[
					-19.70859321853912,
					205.531213991367
				],
				[
					-22.524045162554902,
					205.531213991367
				],
				[
					-25.339497106570686,
					205.531213991367
				],
				[
					-28.154949050586474,
					205.531213991367
				],
				[
					-30.97061579981657,
					205.531213991367
				],
				[
					-33.786067743832355,
					205.531213991367
				],
				[
					-36.60151968784814,
					205.531213991367
				],
				[
					-42.232423575879714,
					202.7155472421369
				],
				[
					-45.048090325109804,
					202.7155472421369
				],
				[
					-47.86354226912559,
					202.7155472421369
				],
				[
					-50.67899421314137,
					199.9000952981211
				],
				[
					-53.49444615715716,
					197.08464335410534
				],
				[
					-56.30989810117295,
					191.45373946607376
				],
				[
					-61.94101679441883,
					183.0071688288121
				],
				[
					-64.75646873843462,
					174.56059819155044
				],
				[
					-67.5719206824504,
					168.9296943035189
				],
				[
					-70.38737262646619,
					160.4831236662572
				],
				[
					-70.38737262646619,
					157.6676717222414
				],
				[
					-70.38737262646619,
					157.6676717222414
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "KZQ_rHnT8elYmXYuYwsSN",
			"type": "freedraw",
			"x": 4784.776716813548,
			"y": 954.4210873023326,
			"width": 33.78585293861804,
			"height": 59.125350045188725,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4g",
			"roundness": null,
			"seed": 1098367743,
			"version": 220,
			"versionNonce": 1606423217,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.8154519440157846,
					-2.815451944015784
				],
				[
					-5.631118693245884,
					-2.815451944015784
				],
				[
					-5.631118693245884,
					-5.630903888031568
				],
				[
					-8.446570637261669,
					-5.630903888031568
				],
				[
					-11.262022581277451,
					-5.630903888031568
				],
				[
					-14.077474525293237,
					-5.630903888031568
				],
				[
					-16.89292646930902,
					-5.630903888031568
				],
				[
					-19.70859321853912,
					-5.630903888031568
				],
				[
					-22.524045162554902,
					-5.630903888031568
				],
				[
					-22.524045162554902,
					-2.815451944015784
				],
				[
					-25.339497106570686,
					-2.815451944015784
				],
				[
					-25.339497106570686,
					0
				],
				[
					-28.154949050586474,
					2.815451944015784
				],
				[
					-28.154949050586474,
					5.630903888031568
				],
				[
					-28.154949050586474,
					11.262022581277451
				],
				[
					-30.970400994602254,
					16.89292646930902
				],
				[
					-30.970400994602254,
					22.524045162554902
				],
				[
					-30.970400994602254,
					25.339497106570683
				],
				[
					-30.970400994602254,
					33.78585293861804
				],
				[
					-30.970400994602254,
					36.60151968784813
				],
				[
					-30.970400994602254,
					39.41697163186392
				],
				[
					-30.970400994602254,
					45.04787551989549
				],
				[
					-28.154949050586474,
					47.863327463911276
				],
				[
					-25.339497106570686,
					47.863327463911276
				],
				[
					-25.339497106570686,
					50.678994213141365
				],
				[
					-22.524045162554902,
					53.49444615715715
				],
				[
					-19.70859321853912,
					53.49444615715715
				],
				[
					-16.89292646930902,
					53.49444615715715
				],
				[
					-14.077474525293237,
					53.49444615715715
				],
				[
					-11.262022581277451,
					53.49444615715715
				],
				[
					-11.262022581277451,
					50.678994213141365
				],
				[
					-8.446570637261669,
					47.863327463911276
				],
				[
					-5.631118693245884,
					45.04787551989549
				],
				[
					-2.8154519440157846,
					39.41697163186392
				],
				[
					-2.8154519440157846,
					36.60151968784813
				],
				[
					-2.8154519440157846,
					30.970400994602254
				],
				[
					0,
					28.15494905058647
				],
				[
					0,
					25.339497106570683
				],
				[
					2.8154519440157846,
					22.524045162554902
				],
				[
					2.8154519440157846,
					16.89292646930902
				],
				[
					2.8154519440157846,
					14.077474525293235
				],
				[
					2.8154519440157846,
					14.077474525293235
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "H5nJVOkti5OT3B5c2p4af",
			"type": "freedraw",
			"x": 4857.979541384029,
			"y": 1143.059160019176,
			"width": 92.91141778902109,
			"height": 109.8043442583301,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4h",
			"roundness": null,
			"seed": 1487211295,
			"version": 239,
			"versionNonce": 1483510929,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8154519440157846
				],
				[
					-2.815451944015785,
					-5.630903888031569
				],
				[
					-8.446570637261669,
					-8.446355832047354
				],
				[
					-14.077474525293239,
					-8.446355832047354
				],
				[
					-16.892926469309025,
					-8.446355832047354
				],
				[
					-25.33949710657069,
					-8.446355832047354
				],
				[
					-36.601519687848146,
					-8.446355832047354
				],
				[
					-42.23242357587972,
					-8.446355832047354
				],
				[
					-50.67899421314138,
					-2.8154519440157846
				],
				[
					-56.309898101172955,
					-2.8154519440157846
				],
				[
					-64.75646873843463,
					2.815666749230099
				],
				[
					-70.3873726264662,
					8.44657063726167
				],
				[
					-73.20282457048198,
					14.077474525293239
				],
				[
					-78.83394326372787,
					16.89314127452334
				],
				[
					-81.64939520774365,
					25.33949710657069
				],
				[
					-84.46484715175944,
					30.970615799816574
				],
				[
					-87.28029909577522,
					39.41697163186394
				],
				[
					-90.095751039791,
					45.04809032510981
				],
				[
					-90.095751039791,
					53.494446157157164
				],
				[
					-92.91141778902109,
					59.125564850403045
				],
				[
					-92.91141778902109,
					64.75646873843462
				],
				[
					-92.91141778902109,
					70.38737262646619
				],
				[
					-92.91141778902109,
					76.01849131971208
				],
				[
					-92.91141778902109,
					84.46484715175944
				],
				[
					-90.095751039791,
					87.28051390098953
				],
				[
					-90.095751039791,
					90.09596584500532
				],
				[
					-90.095751039791,
					92.9114177890211
				],
				[
					-87.28029909577522,
					92.9114177890211
				],
				[
					-87.28029909577522,
					95.72686973303688
				],
				[
					-84.46484715175944,
					98.54232167705267
				],
				[
					-81.64939520774365,
					98.54232167705267
				],
				[
					-76.01827651449777,
					101.35798842628276
				],
				[
					-73.20282457048198,
					101.35798842628276
				],
				[
					-64.75646873843463,
					101.35798842628276
				],
				[
					-56.309898101172955,
					101.35798842628276
				],
				[
					-45.0478755198955,
					101.35798842628276
				],
				[
					-39.41697163186394,
					98.54232167705267
				],
				[
					-36.601519687848146,
					95.72686973303688
				],
				[
					-30.97040099460226,
					92.9114177890211
				],
				[
					-25.33949710657069,
					90.09596584500532
				],
				[
					-22.524045162554906,
					84.46484715175944
				],
				[
					-19.70837841332481,
					81.64939520774365
				],
				[
					-16.892926469309025,
					78.83394326372787
				],
				[
					-16.892926469309025,
					76.01849131971208
				],
				[
					-16.892926469309025,
					73.20303937569629
				],
				[
					-16.892926469309025,
					70.38737262646619
				],
				[
					-14.077474525293239,
					70.38737262646619
				],
				[
					-14.077474525293239,
					67.5719206824504
				],
				[
					-14.077474525293239,
					64.75646873843462
				],
				[
					-14.077474525293239,
					67.5719206824504
				],
				[
					-14.077474525293239,
					73.20303937569629
				],
				[
					-14.077474525293239,
					78.83394326372787
				],
				[
					-14.077474525293239,
					81.64939520774365
				],
				[
					-14.077474525293239,
					87.28051390098953
				],
				[
					-14.077474525293239,
					92.9114177890211
				],
				[
					-14.077474525293239,
					95.72686973303688
				],
				[
					-14.077474525293239,
					98.54232167705267
				],
				[
					-14.077474525293239,
					101.35798842628276
				],
				[
					-14.077474525293239,
					98.54232167705267
				],
				[
					-14.077474525293239,
					98.54232167705267
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "zkMP0JjZKL7vdhdfn-ZN2",
			"type": "freedraw",
			"x": 4818.5625697521655,
			"y": 1219.0776513388887,
			"width": 42.232423575879714,
			"height": 5.631118693245884,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4i",
			"roundness": null,
			"seed": 120868671,
			"version": 186,
			"versionNonce": 1877858929,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					8.446570637261669,
					0
				],
				[
					16.89292646930902,
					0
				],
				[
					25.339497106570686,
					-2.8154519440157846
				],
				[
					30.970400994602254,
					-2.8154519440157846
				],
				[
					36.60151968784814,
					-2.8154519440157846
				],
				[
					39.41697163186393,
					-5.631118693245884
				],
				[
					42.232423575879714,
					-5.631118693245884
				],
				[
					42.232423575879714,
					-5.631118693245884
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "9jjwN5VStNpuH1klf0_GQ",
			"type": "freedraw",
			"x": 4880.503586546583,
			"y": 1128.981685493883,
			"width": 42.232423575879714,
			"height": 90.09596584500531,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4j",
			"roundness": null,
			"seed": 126226271,
			"version": 208,
			"versionNonce": 1997235281,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.815666749230099
				],
				[
					0,
					5.6311186932458845
				],
				[
					0,
					8.446570637261669
				],
				[
					0,
					11.262022581277453
				],
				[
					0,
					16.893141274523337
				],
				[
					0,
					28.154949050586477
				],
				[
					0,
					36.601519687848146
				],
				[
					0,
					45.04809032510981
				],
				[
					0,
					50.67899421314138
				],
				[
					0,
					59.125564850403045
				],
				[
					0,
					64.75646873843463
				],
				[
					0,
					73.20303937569629
				],
				[
					0,
					76.01849131971208
				],
				[
					0,
					78.83394326372787
				],
				[
					0,
					81.64939520774365
				],
				[
					0,
					84.46484715175944
				],
				[
					0,
					87.28051390098952
				],
				[
					2.8154519440157846,
					90.09596584500531
				],
				[
					8.446355832047352,
					90.09596584500531
				],
				[
					11.261807776063138,
					90.09596584500531
				],
				[
					14.077474525293237,
					90.09596584500531
				],
				[
					19.708378413324805,
					90.09596584500531
				],
				[
					22.52383035734059,
					90.09596584500531
				],
				[
					28.154949050586474,
					90.09596584500531
				],
				[
					30.970400994602254,
					90.09596584500531
				],
				[
					33.78585293861804,
					90.09596584500531
				],
				[
					36.601304882633826,
					90.09596584500531
				],
				[
					39.41675682664961,
					90.09596584500531
				],
				[
					42.232423575879714,
					90.09596584500531
				],
				[
					42.232423575879714,
					90.09596584500531
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "2KWk7Sinskpd3U4J9Dzjy",
			"type": "freedraw",
			"x": 4925.55146206648,
			"y": 1140.243708075161,
			"width": 76.01827651449776,
			"height": 76.01849131971207,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4k",
			"roundness": null,
			"seed": 1944767359,
			"version": 233,
			"versionNonce": 966570545,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					5.631118693245884
				],
				[
					0,
					11.262022581277451
				],
				[
					0,
					14.077474525293237
				],
				[
					0,
					19.70859321853912
				],
				[
					0,
					22.524045162554902
				],
				[
					2.8154519440157846,
					28.154949050586474
				],
				[
					2.8154519440157846,
					30.970400994602254
				],
				[
					5.630903888031569,
					36.60151968784814
				],
				[
					5.630903888031569,
					42.232423575879714
				],
				[
					5.630903888031569,
					47.86354226912559
				],
				[
					8.446355832047352,
					50.67899421314137
				],
				[
					8.446355832047352,
					53.49444615715716
				],
				[
					11.262022581277451,
					53.49444615715716
				],
				[
					11.262022581277451,
					56.30989810117295
				],
				[
					14.077474525293237,
					59.125350045188725
				],
				[
					14.077474525293237,
					61.94101679441883
				],
				[
					16.89292646930902,
					61.94101679441883
				],
				[
					19.708378413324805,
					64.75646873843462
				],
				[
					19.708378413324805,
					67.5719206824504
				],
				[
					22.52383035734059,
					70.38737262646619
				],
				[
					25.339497106570686,
					70.38737262646619
				],
				[
					28.154949050586474,
					70.38737262646619
				],
				[
					33.78585293861804,
					70.38737262646619
				],
				[
					39.41697163186393,
					70.38737262646619
				],
				[
					42.232423575879714,
					70.38737262646619
				],
				[
					45.0478755198955,
					67.5719206824504
				],
				[
					50.67877940792706,
					64.75646873843462
				],
				[
					53.49444615715716,
					61.94101679441883
				],
				[
					59.125350045188725,
					59.125350045188725
				],
				[
					61.94080198920451,
					50.67899421314137
				],
				[
					67.5719206824504,
					45.0478755198955
				],
				[
					70.38737262646619,
					36.60151968784814
				],
				[
					73.20282457048197,
					30.970400994602254
				],
				[
					76.01827651449776,
					22.524045162554902
				],
				[
					76.01827651449776,
					19.70859321853912
				],
				[
					76.01827651449776,
					16.89292646930902
				],
				[
					76.01827651449776,
					14.077474525293237
				],
				[
					76.01827651449776,
					11.262022581277451
				],
				[
					76.01827651449776,
					8.446570637261669
				],
				[
					76.01827651449776,
					5.631118693245884
				],
				[
					76.01827651449776,
					2.8154519440157846
				],
				[
					76.01827651449776,
					0
				],
				[
					73.20282457048197,
					2.8154519440157846
				],
				[
					73.20282457048197,
					5.631118693245884
				],
				[
					70.38737262646619,
					14.077474525293237
				],
				[
					70.38737262646619,
					22.524045162554902
				],
				[
					67.5719206824504,
					30.970400994602254
				],
				[
					64.7562539332203,
					39.41697163186393
				],
				[
					64.7562539332203,
					47.86354226912559
				],
				[
					64.7562539332203,
					56.30989810117295
				],
				[
					64.7562539332203,
					61.94101679441883
				],
				[
					64.7562539332203,
					70.38737262646619
				],
				[
					64.7562539332203,
					73.20282457048197
				],
				[
					64.7562539332203,
					76.01849131971207
				],
				[
					64.7562539332203,
					76.01849131971207
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "wx24keUZ",
			"type": "text",
			"x": 5066.325992514197,
			"y": 1064.2252167554484,
			"width": 873.4827270507812,
			"height": 68.27583736975794,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4l",
			"roundness": null,
			"seed": 1218642847,
			"version": 276,
			"versionNonce": 478757905,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"text": "solved via a closed-form solution",
			"rawText": "solved via a closed-form solution",
			"fontSize": 54.620669895806344,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "solved via a closed-form solution",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "BEsP25U3WFN3USSHGFlIG",
			"type": "freedraw",
			"x": 4798.854191338841,
			"y": 1402.0850349729149,
			"width": 73.20282457048197,
			"height": 135.1438413649008,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4m",
			"roundness": null,
			"seed": 635385791,
			"version": 330,
			"versionNonce": 2076744177,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-2.8156667492300986
				],
				[
					0,
					-5.631118693245884
				],
				[
					0,
					-8.446570637261669
				],
				[
					0,
					-11.262022581277451
				],
				[
					-2.8154519440157846,
					-16.893141274523337
				],
				[
					-5.630903888031569,
					-19.70859321853912
				],
				[
					-8.446355832047352,
					-22.524045162554902
				],
				[
					-14.077474525293237,
					-22.524045162554902
				],
				[
					-16.89292646930902,
					-28.154949050586474
				],
				[
					-19.708378413324805,
					-30.97061579981657
				],
				[
					-22.52383035734059,
					-30.97061579981657
				],
				[
					-28.154949050586474,
					-30.97061579981657
				],
				[
					-30.970400994602254,
					-33.786067743832355
				],
				[
					-33.78585293861804,
					-33.786067743832355
				],
				[
					-36.601304882633826,
					-33.786067743832355
				],
				[
					-42.232423575879714,
					-33.786067743832355
				],
				[
					-47.86332746391128,
					-33.786067743832355
				],
				[
					-50.67877940792706,
					-33.786067743832355
				],
				[
					-56.30989810117295,
					-30.97061579981657
				],
				[
					-56.30989810117295,
					-28.154949050586474
				],
				[
					-59.125350045188725,
					-25.339497106570686
				],
				[
					-59.125350045188725,
					-22.524045162554902
				],
				[
					-61.94080198920451,
					-19.70859321853912
				],
				[
					-61.94080198920451,
					-16.893141274523337
				],
				[
					-61.94080198920451,
					-14.077474525293237
				],
				[
					-61.94080198920451,
					-11.262022581277451
				],
				[
					-61.94080198920451,
					-8.446570637261669
				],
				[
					-61.94080198920451,
					-5.631118693245884
				],
				[
					-61.94080198920451,
					0
				],
				[
					-61.94080198920451,
					2.8154519440157846
				],
				[
					-56.30989810117295,
					8.446355832047352
				],
				[
					-50.67877940792706,
					16.89292646930902
				],
				[
					-47.86332746391128,
					22.52383035734059
				],
				[
					-45.0478755198955,
					25.339282301356377
				],
				[
					-36.601304882633826,
					30.970400994602254
				],
				[
					-33.78585293861804,
					33.78585293861804
				],
				[
					-30.970400994602254,
					36.601304882633826
				],
				[
					-25.339497106570686,
					39.41675682664961
				],
				[
					-22.52383035734059,
					42.232423575879714
				],
				[
					-19.708378413324805,
					45.0478755198955
				],
				[
					-16.89292646930902,
					45.0478755198955
				],
				[
					-16.89292646930902,
					50.67877940792706
				],
				[
					-11.262022581277451,
					53.494231351942844
				],
				[
					-8.446355832047352,
					59.125350045188725
				],
				[
					-2.8154519440157846,
					64.7562539332203
				],
				[
					-2.8154519440157846,
					67.57170587723608
				],
				[
					0,
					70.38737262646619
				],
				[
					2.8154519440157846,
					73.20282457048197
				],
				[
					2.8154519440157846,
					76.01827651449776
				],
				[
					5.631118693245884,
					78.83372845851353
				],
				[
					5.631118693245884,
					81.64918040252932
				],
				[
					5.631118693245884,
					84.46484715175943
				],
				[
					8.446570637261669,
					84.46484715175943
				],
				[
					8.446570637261669,
					87.2802990957752
				],
				[
					8.446570637261669,
					90.095751039791
				],
				[
					8.446570637261669,
					92.91120298380677
				],
				[
					5.631118693245884,
					95.72665492782257
				],
				[
					2.8154519440157846,
					98.54232167705266
				],
				[
					0,
					98.54232167705266
				],
				[
					-2.8154519440157846,
					98.54232167705266
				],
				[
					-5.630903888031569,
					101.35777362106843
				],
				[
					-8.446355832047352,
					101.35777362106843
				],
				[
					-11.262022581277451,
					101.35777362106843
				],
				[
					-16.89292646930902,
					101.35777362106843
				],
				[
					-22.52383035734059,
					101.35777362106843
				],
				[
					-30.970400994602254,
					98.54232167705266
				],
				[
					-42.232423575879714,
					95.72665492782257
				],
				[
					-47.86332746391128,
					92.91120298380677
				],
				[
					-53.49444615715716,
					90.095751039791
				],
				[
					-56.30989810117295,
					87.2802990957752
				],
				[
					-59.125350045188725,
					87.2802990957752
				],
				[
					-61.94080198920451,
					87.2802990957752
				],
				[
					-61.94080198920451,
					84.46484715175943
				],
				[
					-64.7562539332203,
					84.46484715175943
				],
				[
					-64.7562539332203,
					84.46484715175943
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "NBbJHGLFL7mK0LVrLpE2H",
			"type": "freedraw",
			"x": 4903.02763170914,
			"y": 1461.2103850181034,
			"width": 50.67899421314137,
			"height": 81.64939520774364,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4n",
			"roundness": null,
			"seed": 1371531231,
			"version": 325,
			"versionNonce": 1214395345,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-5.631118693245884
				],
				[
					0,
					-8.446570637261669
				],
				[
					-2.8156667492300986,
					-8.446570637261669
				],
				[
					-2.8156667492300986,
					-11.262022581277451
				],
				[
					-2.8156667492300986,
					-14.077474525293237
				],
				[
					-5.631118693245884,
					-14.077474525293237
				],
				[
					-8.446570637261669,
					-14.077474525293237
				],
				[
					-11.262022581277451,
					-14.077474525293237
				],
				[
					-16.893141274523337,
					-14.077474525293237
				],
				[
					-19.70859321853912,
					-14.077474525293237
				],
				[
					-22.524045162554902,
					-14.077474525293237
				],
				[
					-28.154949050586474,
					-14.077474525293237
				],
				[
					-30.97061579981657,
					-11.262022581277451
				],
				[
					-33.786067743832355,
					-8.446570637261669
				],
				[
					-36.60151968784814,
					-5.631118693245884
				],
				[
					-39.41697163186393,
					0
				],
				[
					-39.41697163186393,
					2.8154519440157846
				],
				[
					-42.232423575879714,
					2.8154519440157846
				],
				[
					-42.232423575879714,
					5.630903888031569
				],
				[
					-45.048090325109804,
					8.446355832047352
				],
				[
					-45.048090325109804,
					14.077474525293237
				],
				[
					-45.048090325109804,
					16.89292646930902
				],
				[
					-45.048090325109804,
					19.708378413324805
				],
				[
					-45.048090325109804,
					22.52383035734059
				],
				[
					-45.048090325109804,
					28.154949050586474
				],
				[
					-45.048090325109804,
					30.970400994602254
				],
				[
					-45.048090325109804,
					33.78585293861804
				],
				[
					-45.048090325109804,
					36.601304882633826
				],
				[
					-45.048090325109804,
					39.41697163186393
				],
				[
					-42.232423575879714,
					42.232423575879714
				],
				[
					-39.41697163186393,
					45.0478755198955
				],
				[
					-39.41697163186393,
					47.86332746391128
				],
				[
					-36.60151968784814,
					50.67877940792706
				],
				[
					-33.786067743832355,
					50.67877940792706
				],
				[
					-33.786067743832355,
					53.49444615715716
				],
				[
					-33.786067743832355,
					56.30989810117295
				],
				[
					-30.97061579981657,
					56.30989810117295
				],
				[
					-28.154949050586474,
					59.125350045188725
				],
				[
					-25.339497106570686,
					59.125350045188725
				],
				[
					-19.70859321853912,
					61.94080198920451
				],
				[
					-19.70859321853912,
					64.7562539332203
				],
				[
					-16.893141274523337,
					64.7562539332203
				],
				[
					-14.077474525293237,
					64.7562539332203
				],
				[
					-11.262022581277451,
					67.5719206824504
				],
				[
					-8.446570637261669,
					64.7562539332203
				],
				[
					-5.631118693245884,
					61.94080198920451
				],
				[
					-2.8156667492300986,
					56.30989810117295
				],
				[
					0,
					53.49444615715716
				],
				[
					0,
					50.67877940792706
				],
				[
					0,
					47.86332746391128
				],
				[
					2.8154519440157846,
					47.86332746391128
				],
				[
					2.8154519440157846,
					45.0478755198955
				],
				[
					2.8154519440157846,
					42.232423575879714
				],
				[
					2.8154519440157846,
					39.41697163186393
				],
				[
					2.8154519440157846,
					36.601304882633826
				],
				[
					2.8154519440157846,
					33.78585293861804
				],
				[
					2.8154519440157846,
					30.970400994602254
				],
				[
					2.8154519440157846,
					28.154949050586474
				],
				[
					2.8154519440157846,
					30.970400994602254
				],
				[
					5.630903888031569,
					33.78585293861804
				],
				[
					5.630903888031569,
					36.601304882633826
				],
				[
					5.630903888031569,
					42.232423575879714
				],
				[
					5.630903888031569,
					45.0478755198955
				],
				[
					5.630903888031569,
					50.67877940792706
				],
				[
					5.630903888031569,
					56.30989810117295
				],
				[
					5.630903888031569,
					59.125350045188725
				],
				[
					5.630903888031569,
					61.94080198920451
				],
				[
					5.630903888031569,
					64.7562539332203
				],
				[
					5.630903888031569,
					61.94080198920451
				],
				[
					5.630903888031569,
					61.94080198920451
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "-3VU0IPujW3bBRxFWdQ0X",
			"type": "freedraw",
			"x": 4897.396513015893,
			"y": 1489.3653340686892,
			"width": 30.970400994602254,
			"height": 11.262022581277451,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4o",
			"roundness": null,
			"seed": 2052428799,
			"version": 270,
			"versionNonce": 1718456753,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.815451944015784,
					0
				],
				[
					-2.815451944015784,
					2.815451944015784
				],
				[
					0,
					2.815451944015784
				],
				[
					2.815451944015784,
					2.815451944015784
				],
				[
					5.631118693245883,
					0
				],
				[
					8.446570637261667,
					-2.815451944015784
				],
				[
					14.077474525293235,
					-2.815451944015784
				],
				[
					16.89292646930902,
					-5.631118693245882
				],
				[
					19.708593218539118,
					-5.631118693245882
				],
				[
					19.708593218539118,
					-8.446570637261667
				],
				[
					22.524045162554902,
					-8.446570637261667
				],
				[
					25.339497106570683,
					-8.446570637261667
				],
				[
					28.15494905058647,
					-8.446570637261667
				],
				[
					28.15494905058647,
					-8.446570637261667
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "eHKmc3klEW2jwC77WJWMV",
			"type": "freedraw",
			"x": 4948.075507229035,
			"y": 1433.0554359675166,
			"width": 45.0478755198955,
			"height": 90.095751039791,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4p",
			"roundness": null,
			"seed": 933280799,
			"version": 285,
			"versionNonce": 1259484049,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.8154519440157846,
					0
				],
				[
					2.8154519440157846,
					2.8154519440157846
				],
				[
					5.630903888031569,
					8.446355832047352
				],
				[
					5.630903888031569,
					14.077474525293237
				],
				[
					5.630903888031569,
					16.89292646930902
				],
				[
					5.630903888031569,
					22.52383035734059
				],
				[
					5.630903888031569,
					28.154949050586474
				],
				[
					5.630903888031569,
					39.41697163186393
				],
				[
					5.630903888031569,
					47.86332746391128
				],
				[
					5.630903888031569,
					59.125350045188725
				],
				[
					5.630903888031569,
					67.5719206824504
				],
				[
					5.630903888031569,
					76.01827651449776
				],
				[
					5.630903888031569,
					81.64939520774364
				],
				[
					5.630903888031569,
					84.46484715175943
				],
				[
					5.630903888031569,
					87.2802990957752
				],
				[
					5.630903888031569,
					90.095751039791
				],
				[
					8.446355832047352,
					90.095751039791
				],
				[
					11.262022581277451,
					90.095751039791
				],
				[
					14.077474525293237,
					87.2802990957752
				],
				[
					16.89292646930902,
					84.46484715175943
				],
				[
					19.708378413324805,
					84.46484715175943
				],
				[
					25.339497106570686,
					81.64939520774364
				],
				[
					28.154949050586474,
					78.83372845851353
				],
				[
					33.78585293861804,
					78.83372845851353
				],
				[
					36.601304882633826,
					78.83372845851353
				],
				[
					39.41697163186393,
					76.01827651449776
				],
				[
					42.232423575879714,
					76.01827651449776
				],
				[
					45.0478755198955,
					73.20282457048197
				],
				[
					45.0478755198955,
					70.38737262646619
				],
				[
					45.0478755198955,
					70.38737262646619
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "q266d-RyxP_1apY8Ogg_Q",
			"type": "freedraw",
			"x": 5029.724902436778,
			"y": 1435.8708879115325,
			"width": 64.7562539332203,
			"height": 92.91120298380677,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4q",
			"roundness": null,
			"seed": 1301405759,
			"version": 313,
			"versionNonce": 1518836081,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					2.8154519440157846
				],
				[
					0,
					5.630903888031569
				],
				[
					0,
					11.262022581277451
				],
				[
					0,
					16.89292646930902
				],
				[
					0,
					25.339497106570686
				],
				[
					0,
					33.78585293861804
				],
				[
					0,
					42.232423575879714
				],
				[
					0,
					50.67899421314137
				],
				[
					0,
					53.49444615715716
				],
				[
					0,
					56.30989810117295
				],
				[
					0,
					59.125350045188725
				],
				[
					0,
					61.94080198920451
				],
				[
					0,
					64.75646873843462
				],
				[
					0,
					67.5719206824504
				],
				[
					2.8154519440157837,
					67.5719206824504
				],
				[
					5.630903888031567,
					67.5719206824504
				],
				[
					8.446355832047352,
					67.5719206824504
				],
				[
					14.077474525293233,
					67.5719206824504
				],
				[
					16.892926469309018,
					64.75646873843462
				],
				[
					19.708378413324798,
					61.94080198920451
				],
				[
					22.523830357340582,
					61.94080198920451
				],
				[
					28.154949050586467,
					59.125350045188725
				],
				[
					30.97040099460225,
					56.30989810117295
				],
				[
					33.785852938618035,
					56.30989810117295
				],
				[
					36.60130488263382,
					53.49444615715716
				],
				[
					42.2324235758797,
					47.86332746391128
				],
				[
					45.047875519895484,
					45.0478755198955
				],
				[
					47.86332746391127,
					42.232423575879714
				],
				[
					50.67877940792705,
					39.41697163186393
				],
				[
					53.49423135194283,
					33.78585293861804
				],
				[
					56.309898101172934,
					28.154949050586474
				],
				[
					59.125350045188725,
					22.524045162554902
				],
				[
					59.125350045188725,
					16.89292646930902
				],
				[
					61.9408019892045,
					11.262022581277451
				],
				[
					61.9408019892045,
					8.446570637261669
				],
				[
					61.9408019892045,
					5.630903888031569
				],
				[
					61.9408019892045,
					2.8154519440157846
				],
				[
					64.7562539332203,
					2.8154519440157846
				],
				[
					64.7562539332203,
					0
				],
				[
					64.7562539332203,
					-2.8154519440157846
				],
				[
					64.7562539332203,
					-5.630903888031569
				],
				[
					64.7562539332203,
					-2.8154519440157846
				],
				[
					64.7562539332203,
					0
				],
				[
					64.7562539332203,
					8.446570637261669
				],
				[
					64.7562539332203,
					19.708378413324805
				],
				[
					64.7562539332203,
					33.78585293861804
				],
				[
					61.9408019892045,
					47.86332746391128
				],
				[
					61.9408019892045,
					59.125350045188725
				],
				[
					59.125350045188725,
					70.38737262646619
				],
				[
					56.309898101172934,
					78.83394326372786
				],
				[
					56.309898101172934,
					81.64939520774364
				],
				[
					53.49423135194283,
					84.46484715175943
				],
				[
					53.49423135194283,
					87.2802990957752
				],
				[
					53.49423135194283,
					81.64939520774364
				],
				[
					53.49423135194283,
					73.20282457048197
				],
				[
					53.49423135194283,
					64.75646873843462
				],
				[
					53.49423135194283,
					59.125350045188725
				],
				[
					53.49423135194283,
					59.125350045188725
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": null
		},
		{
			"id": "QOqJB7Cp",
			"type": "text",
			"x": 5212.731856460377,
			"y": 1424.6090801354699,
			"width": 671.0128784179688,
			"height": 89.49820256337432,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4r",
			"roundness": null,
			"seed": 772374623,
			"version": 372,
			"versionNonce": 102056785,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"text": "= max(0, S^0_GLU)",
			"rawText": "= max(0, S^0_GLU)",
			"fontSize": 71.59856205069946,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "= max(0, S^0_GLU)",
			"autoResize": true,
			"lineHeight": 1.25
		},
		{
			"id": "EEDxSV4U",
			"type": "text",
			"x": 4694.680965773757,
			"y": 1644.217553846916,
			"width": 1307.603271484375,
			"height": 71.09128931377353,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"IuLQcmnDCJnPPB5IKoXyc"
			],
			"frameId": null,
			"index": "b4s",
			"roundness": null,
			"seed": 987241599,
			"version": 339,
			"versionNonce": 705868081,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1735665508775,
			"link": null,
			"locked": false,
			"text": "Replace any negative entries with 0 effectively",
			"rawText": "Replace any negative entries with 0 effectively",
			"fontSize": 56.873031451018825,
			"fontFamily": 5,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Replace any negative entries with 0 effectively",
			"autoResize": true,
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 5,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"currentItemArrowType": "round",
		"scrollX": 5453.240528064181,
		"scrollY": 4583.712343667916,
		"zoom": {
			"value": 0.1
		},
		"currentItemRoundness": "round",
		"gridSize": 20,
		"gridStep": 5,
		"gridModeEnabled": false,
		"gridColor": {
			"Bold": "rgba(217, 217, 217, 0.5)",
			"Regular": "rgba(230, 230, 230, 0.5)"
		},
		"currentStrokeOptions": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		},
		"objectsSnapModeEnabled": false,
		"activeTool": {
			"type": "selection",
			"customType": null,
			"locked": false,
			"lastActiveTool": null
		}
	},
	"files": {}
}
```
%%