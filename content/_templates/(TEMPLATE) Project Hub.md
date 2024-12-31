---
type: main-note
created: <%tp.date.now("YYYY-MM-DD")%>T<%tp.date.now("HH:mm")%>
tags:
  - concept
  - paper-review
cssclasses:
  - page-white
excalidraw-plugin:
---
<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>

## Project Overview
[Brief description]

## Current Status
- Phase: [e.g., Literature Review]
- Progress: [%]

## Literature Base
```dataview
TABLE created as "Date", tags as "Topics"
FROM "03 RESOURCES"
WHERE contains(file.outlinks, [[{title}]])
SORT created DESC