<%*
// 現在のNoteのタイトルを取得
var noteTitle = window.currentNoteTitle;
if (!noteTitle) {
    noteTitle = await tp.system.prompt("Noteのタイトルを入力してください");
}

// メモのタイトルをプロンプトで入力
var memoTitle = await tp.system.prompt("メモのタイトルを入力してください", noteTitle + "：");

// 入力キャンセル or 空文字チェック
if (!memoTitle || memoTitle.trim() === "") {
  new Notice("タイトル入力がキャンセルされました。処理を中止します。");
  return;
}


// 現在の日付を取得
var currentDate = tp.date.now("YYYY-MM-DD");
var currentDateTime = tp.date.now("YYYY-MM-DD HH:mm");
await tp.file.rename(memoTitle);

// Noteのページのタグを取得（note以外）
var noteTags = window.currentNoteTags || [];

// 基本タグ（Noteのタイトル）を追加
var allTags = [noteTitle, "メモ"];

// Noteのページから継承したタグを追加
noteTags.forEach(tag => {
    if (!allTags.includes(tag)) {
        allTags.push(tag);
    }
});

// タグを文字列に変換
var tagsString = allTags.map(tag => `"${tag}"`).join(", ");

// グローバル変数をクリア
window.currentNoteTitle = null;
window.currentNoteTags = null;

// フロントマターを含む完全なコンテンツを作成
tR += `---
tags: [${tagsString}]
created: ${currentDate}
note_title: "[[N：${noteTitle}]]"
---


# Resouce


# Relations
`;
%>

