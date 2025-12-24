---
title: "Obsidian Bases 入門｜松濤Vimmer"
source: "https://note.com/shotovim/n/n20d31913131b"
author:
  - "[[松濤Vimmer]]"
published: 2025-08-19
created: 2025-12-25
description: "Obsidian Bases が正式にリリースされました！   Introducing Bases, a new core plugin that lets you turn any set of notes into a powerful database.  Now available to everyone with Obsidian 1.9! pic.twitter.com/PXbwzAeO8T — Obsidian (@obsdmd) August 18, 2025  私自身β版から使用しているのですが画像の表示をはじめとしていくつかつまづきポイントがあるので Base"
tags:
  - "clippings"
  - "obsidian"
note:
image: "https://assets.st-note.com/production/uploads/images/209580473/rectangle_large_type_2_e987f00fcbcde07a939591fb75df4cb9.png?fit=bounds&quality=85&width=1280"
---
## メモ

## コンテンツ
![見出し画像](https://assets.st-note.com/production/uploads/images/209580473/rectangle_large_type_2_e987f00fcbcde07a939591fb75df4cb9.png?width=1280)

## Obsidian Bases 入門

[松濤Vimmer](https://note.com/shotovim)

Obsidian Bases が正式にリリースされました！

私自身β版から使用しているのですが画像の表示をはじめとしていくつかつまづきポイントがあるので Bases の使い方を基礎から解説します。また Bases と WebClipper を組み合わせると大変便利なのでそちらの方法についても解説します。

  

## Basesとは

BasesはObsidianが公式で提供している機能で既存のObsidianノートをまとめてデータベースのように扱う事ができるプラグインです。これらはテーブルやカード形式で表現することができます。

## Bases の作成方法

Bases はコマンドパレットを開いて Create new base を選択することで新しく作成することができます。

![](https://assets.st-note.com/img/1755601945-byN2AouP4exZkgQId6m7pswL.png?width=1200)

作成すると以下のように新規の Bases が作成されます。

これで Bases は作成できます。詳細設定は後ほど解説します。

![](https://assets.st-note.com/img/1755601963-DqahpXlijo60KzOwn73mvkCT.png?width=1200)

## Bases の構成

Bases は 2025/08/19 現在テーブルビューとカードビューの 2 つが存在します。これらは画像のように切り替えることが可能です。

![](https://assets.st-note.com/img/1755605012-bmXzEJOBFCRMNShp3jAHZIfo.png?width=1200)

### テーブルビュー

テーブルビューはテーブル形式で表示します。テーブルの設定で行の幅を指定することができます。

![](https://assets.st-note.com/img/1755602028-w6p7a4m0WuPMdrRs8TDlSFfB.png?width=1200)

テーブルビュー一覧

![](https://assets.st-note.com/img/1755602147-Jy3RObwiMnG2apCDuLo4UkK9.png?width=1200)

行の幅の指定

### カードビュー

カードビューはカード形式でデータ一覧を表示します。サムネイル画像など画像を強調させたいときに便利なビューです。

カードビューでは設定でカードの大きさやサムネ画像として扱う画像の設定、画像の比率などの設定ができます。

![](https://assets.st-note.com/img/1755602189-T1DLrYQNFbmBW7ipX6hcndtv.png?width=1200)

カードビュー一覧

![](https://assets.st-note.com/img/1755602303-371e0WGaiHN8nIoZLXOPpVuy.png?width=1200)

カードビューの設定

### Filter

Filter は様々な条件でデータベースに表示するデータをフィルタリングできる機能です。

![](https://assets.st-note.com/img/1755602359-RbhDkpVvyt08crn76uYBoaem.png?width=1200)

Filter には All views と This view があります。All views は作成したすべての View に適用されるフィルターです。This view は現在表示している View にのみ適用されるフィルターです。

カードビューやテーブルビューどちらもに適用したい Filter は All views に、個別の View にのみ適用したいフィルターは This view に設定すると良いでしょう。

以下に比較できる対象と比較演算子を掲載します。これら内容に加えて、フロントマターで設定しているプロパティも比較対象として選択できます。

![](https://assets.st-note.com/img/1755602403-HrjduRvec8UB1qVOFZnykTz3.png?width=1200)

![](https://assets.st-note.com/img/1755602391-mCEkGao3ORJWKcZIPUXV6Nzq.png?width=1200)

**All views に設定したほうがいい内容**

デフォルトで作成した Bases は Markdown 以外のファイルも含まれます。多くの方は Markdown 以外のファイルの表示は不要かと思いますので All views に Markdown 以外を除外する設定をおすすめします。

![](https://assets.st-note.com/img/1755602445-GBIzry6Ffiou9snLv5MtZ0wN.png?width=1200)

jsファイルも認識されてしまう

Filter の選択肢から extension を選択します。これは拡張子にあたります。この extension が markdown と is（イコール）にすることで Markdown ファイルのみを表示することができます。

![](https://assets.st-note.com/img/1755602482-JVfzdq87xDbvLCtmHNXEelhw.png?width=1200)

Markdown以外を除外する設定

### Properties

Properties はデータベースの一覧に表示させる項目を指定します。

デフォルトでは以下内容に加えて、フロントマターで設定しているプロパティが選択できます。

![](https://assets.st-note.com/img/1755602533-FjA4XYQcfPV136L2J9kzBN5C.png?width=1200)

デフォルトで使えるプロパティ

![](https://assets.st-note.com/img/1755602549-CGvq3i5rmfgL0YjZ6Q28NKsz.png?width=1200)

### Formula

Formulaはカスタムしたプロパティを作成できる機能です。

例えばFormulaを使うことでノート内に埋め込んでいる画像を取得することができます

![](https://assets.st-note.com/img/1755602929-rPUtDIpaYEld7wZ95g38ycjv.png?width=1200)

ノート内の画像ファイルを取得するformula

これを適用することで以下のように画像が埋め込んでいるノートから 画像を取得することができます。

![](https://assets.st-note.com/img/1755602945-vntqYHcG6NpB5WQakhj9Iefl.png?width=1200)

実際に画像が埋め込まれているノート

![](https://assets.st-note.com/img/1755602945-rzja5CutXoeiWpLKbUNTc7hl.png?width=1200)

ノートに埋め込まれた画像を取得してimageカラムで表示

ほかにもフロントマターのimageを画像プロパティとして保持することもできます。画像プロパティとして保持することでテーブルビューでも画像を表示することができます。

![](https://assets.st-note.com/img/1755604185-07gIdFhpAO9DqicM1CVRnevr.png?width=1200)

image関数で囲うことで画像プロパティになる

![](https://assets.st-note.com/img/1755604190-bkZEPsYH04UTrBRxVuDJ6Nq3.png?width=1200)

テーブルで画像が表示されている

ここでimage()というものを使用していますが、これはBasesで使える関数になります。以下の関数を始めとして非常に多くの関数を使うことができます。詳細は公式をチェックしてください。

![](https://assets.st-note.com/img/1755604365-ouZ8mMVtdI9OFBU3phYcwxX7.png?width=1200)

[**Functions - Obsidian Help** *Functions are used in Bases to manipulate data from Propertie* *help.obsidian.md*](https://help.obsidian.md/bases/functions)

## Bases の埋め込み

Bases はコードブロックとして書くこともできます。コードブロックで書くことでノート内に Bases を埋め込むことができます。

コードで書くことは難しく思われるかもしれませんが新規で作成した Bases を Cursor などのエディタで開くことで コードとして取得できます。そちらを以下のような形でコードブロックで囲むことでBasesを埋め込むことができます。

![](https://assets.st-note.com/img/1755603040-yK7fJsl4LCGeuPqS10mtI3DV.png?width=1200)

エディアで開いたBasesのファイル

```javascript
\`\`\`base
コピーした内容を貼り付ける
\`\`\`
```
![](https://assets.st-note.com/img/1755603068-dMviphSxm59OE1jbtLaVk4As.png?width=1200)

実際に貼り付けた例

![](https://assets.st-note.com/img/1755603077-SLdYzIxtlHc3BT6v90gWfasq.png?width=1200)

貼り付けるとテーブルが埋め込まれる

## WebClipper と連携

簡単に試せる具体例を紹介します。

ここでは Obsidian Web Clipper で保存した記事を Bases で表示するということを行います。

### WebClipper の設定

Obsidian Web Clipper をインストールします。

[**Obsidian Web Clipper - Chrome Web Store** *Save and highlight web pages in a private and durable format* *chromewebstore.google.com*](https://chromewebstore.google.com/detail/cnjifjpddelmedmihgijeibhnjfabmlf?utm_source=item-share-cb)

デフォルトだと image プロパティがないので追加します。プロパティを追加から以下画像のように追加してください。

![](https://assets.st-note.com/img/1755603172-MwdrWOuqeBc8Nzxn9y5GDPhH.png?width=1200)

imageプロパティ追加前

![](https://assets.st-note.com/img/1755603186-iTGrQa4y7ctVLRloCOE3b6N9.png?width=1200)

imageプロパティ追加後

あとは Obsidian Web Clipper を呼び出して好きな記事を保存してください。

![](https://assets.st-note.com/img/1755603209-EZGKel7I4mJDPvThSbXq6Wt9.png?width=1200)

Obsidian 上でこのようにファイルが追加されていれば保存されています。

![](https://assets.st-note.com/img/1755603221-nxoFw0S2X6G1PUiuZeYAqWLd.png?width=1200)

### Bases の設定

まず Bases を新規で作成してカードビューを作成します。

テーブルビューができるので Filter > All views でフィルタリング設定をします（先にカードビューを作成して This view でフィルタリングしても問題ないです）。

また任意ですがファイルが多い方は folder プロパティを用いることで指定したフォルダ内のファイルのみ表示できるので設定してください。

![](https://assets.st-note.com/img/1755603247-0rYPnZHz9gOa5BSFLRkqeKyW.png?width=1200)

カードビューを作成します。Table と書いてある部分をクリックして Add view して Layout を Card にしてください。

![](https://assets.st-note.com/img/1755603266-wOZQnrh9LRSToGMqNx5tp7ld.png?width=1200)

Image property に image を選択してください（image が存在しない場合、Web Clip で image プロパティがうまく作成できていない可能性があります）。

また Image fit を Contain にしてください。Contain にすることでカードにフィットして画像が表示されます。

![](https://assets.st-note.com/img/1755603281-Lvf89lI2ngAzwu3d5omPqtEc.png?width=1200)

これによって以下のようなカードを作成することができます。

![](https://assets.st-note.com/img/1755603319-Tv1aOAiWEq3RbsDrSYFHZ60m.png?width=1200)

あとは多くの記事を WebClip したり表示するプロパティをふやすことで以下のようにギャラリーを作成することができます。

![](https://assets.st-note.com/img/1755602189-T1DLrYQNFbmBW7ipX6hcndtv.png?width=1200)

## まとめ

今回はObsidianの新機能Basesを紹介しました。いままでDataviewで表現していたようなギャラリービューが簡単に表現できるようになり、ますますObsidianの活用の幅が広がったかなと思います。特にFormula機能を駆使することでいろいろな形でデータベースを表現することができます。是非Basesをお試しください！

## 参考

[**Introduction to Bases - Obsidian Help** *Create database-like views of your notes, formatted as tables* *help.obsidian.md*](https://help.obsidian.md/bases)