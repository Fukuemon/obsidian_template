---
tags:
  - book
  - Obsidian_Zenn
link: https://zenn.dev/estra/books/obsidian-dot-zenn/viewer/2-oz-what-is-obsidian
image: https://res.cloudinary.com/zenn/image/upload/s--Y_oUBVPv--/g_center%2Ch_280%2Cl_fetch:aHR0cHM6Ly9zdG9yYWdlLmdvb2dsZWFwaXMuY29tL3plbm4tdXNlci11cGxvYWQvYm9va19jb3Zlci82ZWMzMDNhMjkyLnBuZw==%2Cw_200/v1627283836/default/og-base-book_yz4z02.jpg?_a=BACAGSGT
---
![[Pasted image 20251225031818.png]]


## 読書メモ
```dataview
TABLE file.cday AS "作成日",
	  file.mday AS "修正日"
FROM #Obsidian_Zenn and #読書メモ
SORT file.bookName desc
```

```dataviewjs
const btn = dv.el("button", "本のメモを作成")
btn.onclick = async function(){
	// 現在のページのタイトル（本のタイトル）を取得
	const currentPageTitle = dv.current().file.name;
	const baseTitle = currentPageTitle.replace(/^📕：/, "");
	
	// タイトルが空（ファイル名変更ミスや手動修正など）なら停止
  if (!baseTitle) {
    new Notice("タイトルが空のため、メモ作成を中止します。");
    return;
  }
  
  // 現在のページのタグを取得
  const currentPageTags = dv.current().file.tags || [];
  
  // "book"タグを除外し、本のタイトル自体のタグを追加
  const filteredTags = currentPageTags
    .filter(tag => tag !== "#book" && tag !== "book") // #付きと無し両方をチェック
    .map(tag => tag.startsWith("#") ? tag.substring(1) : tag); // #を除去
  
  // 本のタイトルをタグとして追加（重複チェック）
  if (!filteredTags.includes(baseTitle)) {
    filteredTags.push(displayBookName);
  }
  
  try {
    // 本のタイトルとタグ情報をTemplaterで使用できるように設定
    window.currentBookTitle = baseTitle;
    window.currentBookTags = filteredTags;
    
    // テンプレートファイルのパスを指定
    const templatePath = "999_Template/bookMemo.md";
    const templateFile = app.vault.getAbstractFileByPath(templatePath);
    
    if (!templateFile) {
      new Notice("テンプレートファイルが見つかりません: " + templatePath);
      window.currentBookTitle = null;
      window.currentBookTags = null;
      return;
    }
    
    // Templaterプラグインのインスタンスを取得
    const templaterPlugin = app.plugins.plugins["templater-obsidian"];
    if (!templaterPlugin) {
      new Notice("Templaterプラグインが見つかりません");
      window.currentBookTitle = null;
      window.currentBookTags = null;
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
    window.currentBookTitle = null;
    window.currentBookTags = null;
  }
}
```

