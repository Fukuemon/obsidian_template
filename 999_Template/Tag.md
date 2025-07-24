<%* 
var tagName = await tp.system.prompt("タグ名"); 
await tp.file.rename(tagName);

// 全体を文字列として出力
tR += `---
tags:
  - moc
  - ${tagName}
---

## Notes
\`\`\`dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #${tagName}
WHERE contains(file.tags, "note")
SORT file.mday desc
\`\`\`

## Memos
\`\`\`dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #${tagName}
WHERE !contains(file.tags, "clippings") and !contains(file.tags, "note")
SORT file.mday desc
\`\`\`

## Literatures
\`\`\`dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #${tagName}
WHERE contains(file.tags, "clippings")
SORT file.mday desc
\`\`\``;
%>