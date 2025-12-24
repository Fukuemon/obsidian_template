---
tags:
  - note
  - Obsidianのすゝめ
  - obsidian
note_status: 随筆
---
## 概要
~~みんなに Obsidian を使ってもらうための記事~~
ではなく、どうしてメモを取る必要があるのか。
なぜ Obsidian がいいのかについて自分の考えを書く。
ポエムのような内容を含める。
その後、自分の Obsidian の使い方について Tips 形式で記述していく

## 目次

1. はじめに
2. 前半：なぜメモを取る必要があるのか(知識管理が大切なのか)
3. 後半：私の Obsidian 活用


## 関連メモ
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #Obsidianのすゝめ and #メモ
SORT file.cday desc
```

```dataviewjs
const btn = dv.el("button", "メモを作成")
btn.onclick = async function(){
	// 現在のページのタイトルを取得
	const currentPageTitle = dv.current().file.name;
	const baseTitle = currentPageTitle.replace(/^N：/, "");
	
	// タイトルが空なら停止
  if (!baseTitle) {
    new Notice("タイトルが空のため、メモ作成を中止します。");
    return;
  }
  
  // 現在のページのタグを取得
  const currentPageTags = dv.current().file.tags || [];
  // "note"タグを除外
  const filteredTags = currentPageTags
    .filter(tag => tag !== "#note" && tag !== "note") // #付きと無し両方をチェック
    .map(tag => tag.startsWith("#") ? tag.substring(1) : tag); // #を除去
  
  // Noteのタイトルをタグとして追加（重複チェック）
  if (!filteredTags.includes(baseTitle)) {
    filteredTags.push(baseTitle);
  }
  
  try {
    // Noteのタイトルとタグ情報をTemplaterで使用できるように設定
    window.currentNoteTitle = baseTitle;
    window.currentNoteTags = filteredTags;
    
    // テンプレートファイルのパスを指定
    const templatePath = "999_Template/memo.md";
    const templateFile = app.vault.getAbstractFileByPath(templatePath);
    
    if (!templateFile) {
      new Notice("テンプレートファイルが見つかりません: " + templatePath);
      window.currentNoteTitle = null;
      window.currentNoteTags = null;
      return;
    }
    
    // Templaterプラグインのインスタンスを取得
    const templaterPlugin = app.plugins.plugins["templater-obsidian"];
    if (!templaterPlugin) {
      new Notice("Templaterプラグインが見つかりません");
      window.currentNoteTitle = null;
      window.currentNoteTags = null;
      return;
    }
    
    // 指定したテンプレートから新しいファイルを作成
    await templaterPlugin.templater.create_new_note_from_template(templateFile);
    
    // 成功通知
    new Notice(`「${baseTitle}」のメモを作成しました`);
    
  } catch (error) {
    console.error("テンプレート実行エラー:", error);
    new Notice("テンプレートの実行に失敗しました: " + error.message);
    // エラー時にグローバル変数をクリア
    window.currentNoteTitle = null;
    window.currentNoteTags = null;
  }
}
```

   