---
date: <%tp.date.now("YYYY-MM-DD")%>T<%tp.date.now("HH:mm")%>
tags:
  - Notes
cssclasses:
  - page-manila
---

<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>

