---
date: <%tp.date.now("YYYY-MM-DD")%>T<%tp.date.now("HH:mm")%>
tags:
  - Meeting
cssclasses:
  - page-white
---

<%*
	let title = tp.file.title 
	if (title.startsWith("Untitled")) {
		title = await tp.system.prompt("Title");
		await tp.file.rename(`${title}`);
	}
%>

# Meeting over here