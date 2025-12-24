<%*
// 現在の本のタイトルを取得
var bookTitle = window.currentBookTitle;
if (!bookTitle) {
    bookTitle = await tp.system.prompt("本のタイトルを入力してください");
}

// メモのタイトルをプロンプトで入力
var memoTitle = await tp.system.prompt("メモのタイトルを入力してください", bookTitle + "：");

// 現在の日付を取得
var currentDate = tp.date.now("YYYY-MM-DD");
var currentDateTime = tp.date.now("YYYY-MM-DD HH:mm");
await tp.file.rename(memoTitle);

// 本のページのタグを取得（book以外）
var bookTags = window.currentBookTags || [];

// 基本タグ（本のタイトルと読書メモ）を追加
var allTags = [bookTitle, "読書メモ"];

// 本のページから継承したタグを追加
bookTags.forEach(tag => {
    if (!allTags.includes(tag)) {
        allTags.push(tag);
    }
});

// タグを文字列に変換
var tagsString = allTags.map(tag => `"${tag}"`).join(", ");

// グローバル変数をクリア
window.currentBookTitle = null;
window.currentBookTags = null;

// フロントマターを含む完全なコンテンツを作成
tR += `---
tags: [${tagsString}]
created: ${currentDate}
book_title: "[[📕：${bookTitle}]]"
---
## メモ
---

### 重要なポイント
- 

### 印象的な引用
> 

### 自分の感想・考察
- 

## 📋 アクションアイテム
---
- [ ] 

## Resource
---

## Relation
---`;
%>
