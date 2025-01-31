---
layout: ../../layouts/MarkdownPostLayout.astro
title: AstroでER図を正しく描画する手順
author: 湯浅信彦
description: 力技でAstroでER図を描画できるようにしたが、まだ課題は残る
image:  
  url:  /fuyubae.jpeg
  alt:  冬映えの朝
pubDate: 2025-01-31
tags: ["DB設計","ER図","Astro Tips"]
---

<style>
  #naki {
    font-size:1.6rem;
  }
</style>

## AstroのMermaid対応に関係していそうなファイルを特定する

1. src/layouts/MarkdownPostLayout.astro
1. src/pages/posts/post-7.md
1. src/styles/global.css

### 解決手順

#### 1.mermaid.min.jsファイルを新規作成
  - src/scripts/mermaid.min.jsファイルを新規に作成する  
  - ファイルの中身はCDNをアクセスして全部コピーして新規作成したファイルにペースト  
    ※CDNのurl : https://unpkg.com/mermaid@11.4.1/dist/mermaid.min.js

#### 2.Astroプロジェクト内の関連していそうなファイルを編集する

編集内容の詳細は、それぞれのリンク先を参照してください。

1. <a href="https://github.com/yuasys/astro-2024-tutorial/commit/783cfad786326ad6a0dd41547dd9f8a7e9b759a9#diff-bb0a91360a5fa7f1097b41c0bace94a5c4a1a0cdb7fec8d4dd1211c46695c911">src/layouts/MarkdownPostLayout.astro</a>

1. <a href="https://github.com/yuasys/astro-2024-tutorial/commit/783cfad786326ad6a0dd41547dd9f8a7e9b759a9#diff-f807ae8b70f653aa25c5f1726e21cb42c64d1605e501fa0788554fbd907654c7">src/styles/global.css</a>

1. <a href="https://github.com/yuasys/astro-2024-tutorial/commit/783cfad786326ad6a0dd41547dd9f8a7e9b759a9#diff-f807ae8b70f653aa25c5f1726e21cb42c64d1605e501fa0788554fbd907654c7">src/pages/posts/post-7.md</a>

    📌特に61行〜86行に注目してください。書式が変わっています。  

  |Astro書式|Github書式|メモ|
  |----|----|----|
  |```<pre class="mermaid">```タグと<br> ```</pre>```タグでコンテンツをはさむ|\`\`\`mermaid と<br/>\`\`\`でコンテンツをはさむ|GitHub書式はズーム機能など<br>豊富な機能を備えている|


## 残された課題

😢下の画像のような「ワケワカラン」エラーが出て気持ち悪い。でも実害はなさそうだから、、、

<img src="/errorMSG_20250131_0731.png" width="50%" alt="エラーメッセージ" />

