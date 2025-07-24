---
tags:
  - daily
Date: <% tp.file.creation_date("YYYY/MM/DD HH:mm:ss") %>
---
## {{date:YYYY-MM-DD(ddd)}}日誌

### 今日の作業
- [ ] 


### Memos

 
## 📁 Created Files
---
```dataview
LIST 
FROM ""　AND -"100-daily notes"
WHERE file.cday = this.file.day
SORT file.mtime ASC
```

## 📁 Modified Files
---
```dataview
LIST 
FROM ""　AND -"100-daily notes"
WHERE file.mday = this.file.day AND file.cday != this.file.day
SORT file.mtime ASC
```