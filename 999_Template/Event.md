<%* 
var eventName = await tp.system.prompt("イベント名"); 
var eventDate = await tp.system.prompt("開催日（YYYYMMDD形式", tp.file.creation_date("YYYYMMDD"));

if (!eventName || !eventDate) return;

// 日付形式をチェック（8桁の数字）
if (!/^\d{8}$/.test(eventDate)) {
    new Notice("日付は8桁の数字（YYYYMMDD）で入力してください");
    return;
}

const fileName = eventDate + "_" + eventName;
await tp.file.rename(fileName);

// 日付を見やすい形式に変換
const formattedDate = eventDate.replace(/(\d{4})(\d{2})(\d{2})/, '$1年$2月$3日');

tR += `---
tags:
  - event
event_date: ${eventDate}
登壇: false
---
EventPage：


## Resource


## Relations`;
%>