---
cssclasses:
  - page-manila
date: <%tp.date.now("YYYY-MM-DD")%>T<%tp.date.now("HH:mm")%>
tags:
  - paper-review
  - source
---

# {{title}}

# Metadata
Author: {{authors}}
Item type: {{itemType}}
Citekey: {{citekey}}
Publish date: {{date | format("YYYY")}}
Publication: {{publicationTitle}}
DOI: {{DOI}}
URL: {{url}}
Accessed: {{accessDate | format("YYYY-MM-DD")}}
PDF Link: {{pdfZoteroLink}}


## Summary
[One paragraph summary]

## Key Points
- 

## Methods
- 

## Results
- 

## Research Gaps
- 

## Links to My Research
- [Link to my research]

# Annotations
Created: <% tp.date.now() %>

{% for annotation in annotations %}
---
{% if annotation.annotatedText %}
> {{annotation.annotatedText}}
[Page {{annotation.page}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.page}}&annotation={{annotation.id}})
**Color**: {{annotation.colorCategory}}
{% endif %}

{% if annotation.imageRelativePath %}
![[{{annotation.imageRelativePath}}]]
**Page**: {annotation.page}
**Color**: {{annotation.colorCategory}}

{% endif %}

{% if annotation.comment %}
**Comment**: {{annotation.comment}}
**Page**: {{annotation.page}}
**Color**: {{annotation.colorCategory}}
{% endif %}

{% if annotation.allTags %}
**Tags**: {{annotation.allTags}}
{% endif %}

{% endfor %}