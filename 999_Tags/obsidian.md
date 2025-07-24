---
tags:
  - moc
  - obsidian
---

## Notes
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #obsidian
WHERE contains(file.tags, "note")
SORT file.mday desc
```

## Memos
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #obsidian
WHERE !contains(file.tags, "clippings") and !contains(file.tags, "note")
SORT file.mday desc
```

## Literatures
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #obsidian
WHERE contains(file.tags, "clippings")
SORT file.mday desc
```