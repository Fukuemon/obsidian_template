---
tags:
  - 2025/04/03
  - moc
  - obsidian
---
## Memo
- 

## Notes
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #obsidian
SORT file.mday desc
```