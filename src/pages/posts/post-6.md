---
layout: ../../layouts/MarkdownPostLayout.astro
title: フェンス内の書き方でエラー防止
author: 湯浅信彦
description: 項目の値をnullにするとNetlifyのbuild時にエラー発生
image:  
  url:  
  alt:  
pubDate: 2025-01-29
tags: ["Astro Tips","フェンス記法"]
---

### Netlifyにデプロイ時にbuildエラーになったフェンス記述例
```
---
layout: ../../layouts/MarkdownPostLayout.astro
title: チュートリアルの次にやること
author: 湯浅信彦
description:
image:
  url:
  alt:
pubDate: 2025-01-26
tags: ["astro", "Astroブログ運用試験"]
---
```

**解説**  
上記の例では、```description```項目がnullになっているため、Netlifyでのbuild実行でエラー停止となった。  
```image,url,alt```などの各項目においては値がなくてもエラーにならなかった。  

📌ローカル実行環境で```npm run dev```しても問題が発生しないので、気づきにくい点に留意すること
