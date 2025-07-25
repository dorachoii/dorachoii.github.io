---
layout: post
title: "[Qiita] WebGL と GLSL で始める、はじめてのシェーダコーディング"
date: 2025-07-10 12:17:00 +0900
categories:
  - ブログ読み
tags:
  - read-daily
toc:
---

## 📖 今日の記事  
[やってみれば超簡単！ WebGL と GLSL で始める、はじめてのシェーダコーディング（１）](https://qiita.com/doxas/items/b8221e92a2bfdc6fc211)
[やってみれば超簡単！ WebGL と GLSL で始める、はじめてのシェーダコーディング（２）](https://qiita.com/doxas/items/f34325520d1aa5af4692)

---

## 🗒️ 単語

| 単語            | 意味             | 文章                                 |
| ------------- | -------------- | ---------------------------------- |
| 払拭（ふっしょく）     | 불식             | 漠然とした **難しそう感** を払拭すべく             |
| 刺さる（ささる）      | 꽂히다, 공감되다      | この記事は自分に刺さる記事となっております              |
| 敷居（しきい）       | 문턱             | 初心者には敷居が高いのかなと思います。                |
| もはや           | 이제는            | もはやブラウザとネット環境さえあればシェーダが書けます。       |
| 走る            | 실행되다           | シェーダが走るという仕組みです。                   |
| 描き出される        | 렌더링되다          | —                                  |
| 映し出される        | 투사되다           | —                                  |
| 格納（かくのう）      | 저장             | データがあらかじめ格納されています。                 |
| 凝らす（こらす）      | 정성을 들이다        | 各自が修正して創意工夫を凝らすのは、                 |
| 解釈（かいしゃく）     | 해석             | そのまま RGBA として解釈され、                 |
| 紫（むらさき）       | 보라색            | —                                  |
| 操る（あやつる）      |                | 色を自在に操る                            |
| べた塗り          |                | 画面にべた塗りで色を付けることしかできないのでは面白くありません。  |
| 覆う（おおう）       |                | スクリーン全体を覆う一枚の大きなポリゴンがレンダリングされています。 |
| いかにも          |                | いかにも大変な負荷が掛かってしまいそう                |
| 見張る           | 크게 뜨다.휘둥그레 지다. | 近年のハードウェアの進化には目を見張るばかりです。          |
| 勘             | 직감력            | 勘のいい人ならわかったかもしれませんが                |
| 紛らわしい（まぎらわしい） | 헷갈리기 쉽다        | 最初はちょっと紛らわしく感じるかもしれません。            |
| 陥り（おちいり）      | 빠지다            | 初心者のうちに陥りやすい失敗                     |



---

## 💡 インサイト

- たとえば Unity などのツール、あるいはマインクラフトのようなゲーム、またはモデリングソフトなどでもシェーダを自分で記述することができるような世の中です。きっとシェーダに触れた経験は無駄にはならないでしょう。
- GLSL は 昨今話題の WebGL でも採用されているので、特別な開発環境の準備などをしなくても、ブラウザとテキストエディタさえあれば簡単に始められます。
- どのような複雑な計算をしようとも、最終的にどんな色を出力するのかを決めることが最終的な目的なのです。
- フラグメントシェーダには、前回から言っているように画面に出力する色を決定するという役割があります。
- 通常、CANVAS の 2D コンテキストなどでは、左上が原点になります。GLSL の中身ではこれが上下反転している
- 普通に数学的に考えると何もおかしなところはないのですが、GLSL は数値の扱いが非常に厳密です。先ほどのコードの場合、浮動小数点数の型である `vec2` 型の `gl_FragCoord` の値を、整数型の数値で割り算しようとしているので、異なる型で計算しようとしている点が引っかかってしまうのです。
- なぜなら、`vec` 系の変数型は、内部的には全て `float` として扱われるので、特別な理由がない限りは整数を利用しないほうがうっかりミスによるエラーが起こりにくいからです。
