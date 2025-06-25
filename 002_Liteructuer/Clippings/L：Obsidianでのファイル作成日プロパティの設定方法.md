---
title: "Obsidianでのファイル作成日プロパティの設定方法"
source: "https://www.genspark.ai/spark/obsidian%E3%81%A7%E3%81%AE%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E4%BD%9C%E6%88%90%E6%97%A5%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95/c64c4dd8-103f-4937-bf12-f838d73064f7"
author:
published:
created: 2025-06-23
description: "Obsidianでのファイル作成日プロパティの設定方法"
tags:
  - "clippings obsidian"
Note: "[[]]"
---
何でも聞いてください

Obsidianでのファイル作成日プロパティの設定方法

Genspark

Aug 16, 2024

情報

Obsidianのpropertyのcreation dateを取得するためには、 `2025-06-23 18:13` を使用することが適切です。このテンプレートタグは、ファイルの作成日を取得するための標準的な方法です。以下に詳細を説明します。

### 使用方法とフォーマット

`2025-06-23 18:13` は、ファイルの作成日を取得するためのテンプレートコードです。このコードは、デフォルトで「YYYY-MM-DD HH:mm」の形式で日付を返します。フォーマットを変更したい場合は、引数としてフォーマット文字列を指定することができます。

#### 例:

- デフォルト形式で取得:
	```markdown
	2025-06-23 18:13
	```
- カスタム形式で取得:
	```markdown
	月曜日 23日 6月 2025 18:13
	```

### よくある問題と解決策

1. **日付が正しく表示されない場合**:
	- フォーマット文字列が正しくない可能性があります。Moment.jsのフォーマットリファレンスを参照して、正しい形式を使用してください [1](https://www.reddit.com/r/ObsidianMD/comments/16hgg0n/properties_creation_date_modification_date/ "Reddit · r/ObsidianMD") [2](https://forum.obsidian.md/t/how-to-retrieve-creation-date-from-metadata-of-a-note/31246 "Obsidian Forum") 。
	- ファイルの作成日が取得できない場合、「1 January 1970」と表示されることがあります。この場合、エラーメッセージや警告が表示されるべきですが、現時点ではそのような機能は実装されていません [3](https://forum.obsidian.md/t/wrong-creation-date-properties-dataview-lists-wrong-date/79176 "Obsidian Forum") 。
2. **テンプレートのプロパティに追加する場合**:
	- プロパティに追加する際には、YAMLフロントマターに以下のように記述します。
		```yaml
		---
		created: 2025/06/23 18:13:21
		---
		```
	- ただし、自己更新コード（例： `NaN` ）はプロパティ内ではサポートされていません [4](https://forum.obsidian.md/t/yaml-timestamp-creation-date/67167 "Obsidian Forum") 。

### 参考情報

- `tp.file.creation_date()` は、ファイルの作成日を取得するための標準的な方法です [5](https://obsidian.rocks/tracking-note-dates-in-obsidian/ "Obsidian Rocks") 。
- フォーマットオプションについては、Moment.jsのドキュメントを参照してください。

この情報が役立つことを願っています。何か他に質問があれば、お知らせください。

目次

Obsidianのpropertyのcreation dateを取得するためには、 `2025-06-23 18:13` を使用することが適切です。このテンプレートタグは、ファイルの作成日を取得するための標準的な方法です。以下に詳細を説明します。

### 使用方法とフォーマット

`2025-06-23 18:13` は、ファイルの作成日を取得するためのテンプレートコードです。このコードは、デフォルトで「YYYY-MM-DD HH:mm」の形式で日付を返します。フォーマットを変更したい場合は、引数としてフォーマット文字列を指定することができます。

#### 例:

- デフォルト形式で取得:
	```markdown
	2025-06-23 18:13
	```
- カスタム形式で取得:
	```markdown
	月曜日 23日 6月 2025 18:13
	```

### よくある問題と解決策

1. **日付が正しく表示されない場合**:
	- フォーマット文字列が正しくない可能性があります。Moment.jsのフォーマットリファレンスを参照して、正しい形式を使用してください [1](https://www.reddit.com/r/ObsidianMD/comments/16hgg0n/properties_creation_date_modification_date/ "Reddit · r/ObsidianMD") [2](https://forum.obsidian.md/t/how-to-retrieve-creation-date-from-metadata-of-a-note/31246 "Obsidian Forum") 。
	- ファイルの作成日が取得できない場合、「1 January 1970」と表示されることがあります。この場合、エラーメッセージや警告が表示されるべきですが、現時点ではそのような機能は実装されていません [3](https://forum.obsidian.md/t/wrong-creation-date-properties-dataview-lists-wrong-date/79176 "Obsidian Forum") 。
2. **テンプレートのプロパティに追加する場合**:
	- プロパティに追加する際には、YAMLフロントマターに以下のように記述します。
		```yaml
		---
		created: 2025/06/23 18:13:21
		---
		```
	- ただし、自己更新コード（例： `NaN` ）はプロパティ内ではサポートされていません [4](https://forum.obsidian.md/t/yaml-timestamp-creation-date/67167 "Obsidian Forum") 。

### 参考情報

- `tp.file.creation_date()` は、ファイルの作成日を取得するための標準的な方法です [5](https://obsidian.rocks/tracking-note-dates-in-obsidian/ "Obsidian Rocks") 。
- フォーマットオプションについては、Moment.jsのドキュメントを参照してください。

この情報が役立つことを願っています。何か他に質問があれば、お知らせください。

### もっと詳しく[1](https://www.reddit.com/r/ObsidianMD/comments/16hgg0n/properties_creation_date_modification_date/)

[

www.reddit.com

](https://www.reddit.com/r/ObsidianMD/comments/16hgg0n/properties_creation_date_modification_date/)[

2

forum.obsidian.md

](https://forum.obsidian.md/t/how-to-retrieve-creation-date-from-metadata-of-a-note/31246)[

3

forum.obsidian.md

](https://forum.obsidian.md/t/wrong-creation-date-properties-dataview-lists-wrong-date/79176)[

4

forum.obsidian.md

](https://forum.obsidian.md/t/yaml-timestamp-creation-date/67167)[

5

obsidian.rocks

](https://obsidian.rocks/tracking-note-dates-in-obsidian/)

投稿するためにサインアップ

Genspark エージェントをアンロック  
AI スライド • AI シート • AI チャット & その他

サインアップ

無料です

Googleでサインアップ