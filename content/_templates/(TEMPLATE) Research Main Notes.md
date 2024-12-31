---
type: main-note
created: <%tp.date.now("YYYY-MM-DD")%>T<%tp.date.now("HH:mm")%>
tags:
  - concept
  - HSU
  - paper-review
cssclasses:
  - page-white
excalidraw-plugin: parsed
---
<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>

## {{tp.file.title}}
## Core Concept
[One paragraph, max 100 words]

## Source
- [[{{source}}]]

## Connections
- Project: [[Nearly Blind Hyperspectral]]
- Related Notes: 

## Questions & Ideas
- 

## Tags
#concept #hyperspectral