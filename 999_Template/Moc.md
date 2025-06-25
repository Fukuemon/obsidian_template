---
tags:
  - 2025/04/03
  - moc
  - <% tp.file.title %>
---
## Memo
- 

## Notes
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #<% tp.file.title %>
SORT file.mday desc
```