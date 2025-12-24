---
title: "Introduction - Templater"
source: "https://silentvoid13.github.io/Templater/"
author:
published:
created: 2025-12-25
description:
tags:
  - "clippings"
  - "obsidian"
  - "templater"
note:
image:
---
## メモ

## コンテンツ
[Templater](https://github.com/SilentVoid13/Templater) is a template language that lets you insert **variables** and **functions** results into your notes. It will also let you execute JavaScript code manipulating those variables and functions.

With [Templater](https://github.com/SilentVoid13/Templater), you will be able to create powerful templates to automate manual tasks.

The following template file, that is using [Templater](https://github.com/SilentVoid13/Templater) syntax:

```javascript
---
creation date: 2025-12-25 03:04
modification date: 木曜日 25日 12月 2025 03:04:13
---

<< [[2025-12-24]] | [[2025-12-26]] >>

# 🌐：Introduction - Templater

> [!quote] One must be fond of people and trust them if one is not to make a mess of life.
> — E. M. Forster
```

Will produce the following result when inserted:

```javascript
---
creation date: 2021-01-07 17:20
modification date: Thursday 7th January 2021 17:20:43
---

<< [[2021-04-08]] | [[2021-04-10]] >>

# Test Test

> Do the best you can until you know better. Then when you know better, do better.
> &mdash; <cite>Maya Angelou</cite>
```