---
layout: post
title: "[Qiita] GoF デザインパターン チートシート"
---

## 📖 今日の記事  
[GoF デザインパターン チートシート](https://qiita.com/tanakahisateru/items/df03d2558f9499d1a64a)

---

## 🗒️ 単語

| 単語          | 意味                  | 文章                                                       |
| ----------- | ------------------- | -------------------------------------------------------- |
| 肩書(かたがき)    | 세로로 쓴 명함‧서류 등에서) 성명 | 出版された本に「オブジェクト指向における再利用のための」という肩書が付いていましたが、これが本当に良くなかった。 |
| 褒める（ほめる）    |                     |                                                          |
| 信仰（しんこう）    | 신앙                  | 「オブジェクト指向様こそが良い設計のすべて教」が信仰されていました。                       |
| 迷信（めいしん）    | 미신                  | 迷信がはびこった                                                 |
| はびこる        | 무성하다                |                                                          |
| 再燃(さいねん)    | 다시 타올랐다             | いま日本では DDD (ドメイン駆動設計) が再燃していますが                          |
| 諦め(あきらめる)   |                     |                                                          |
| 称する（しょうする）  | 일컫다                 | 軽量 DDD と称して DDD のデザインパターンだけを利用しようとしています。                 |
| 疎結合（そけつごう）  | 헐거운 커플링             | 疎結合にした先をビジネスの本質に一致させようとする意識がないまま、                        |
| 愚直（ぐちょく）    | 우직.                 |                                                          |
| 文脈（ぶんみゃく（）） |                     | なんて文脈ひどない?                                               |
| 省ける（はぶける）   | 없애다                 | どれだけみんなへの説明を省けるかなのです。                                    |
| 醍醐味（だいごみ）   | 묘미                  | オブジェクト指向の醍醐味                                             |
| 尻目（しりめ）     | 곁눈                  | 流行りに乗ったけどうまく行かなかった人たちを尻目に                                |
| 語彙（ごい）      | 어휘                  | チームに共通の語彙を形成しいくのです。                                      |
| 諺（ことわざ）     | 속담                  |                                                          |



---

## 💡 インサイト

- デザインパターンを盛り込んだ方がソフトウェアが高級になるらしい、なんてとんでもない迷信がはびこったのです。目的のないパターンはただの難読化です。
- HTTP ミドルウェアは Proxy パターンですね。CQRS とかいうアレの C はまさに Command です。たいていのフレームワークは Template Method パターンを利用しています。最重要パターン、Abstract Factory は、オブジェクト指向の醍醐味、操作と生成の分離の概念が難しかったのを、一言で表せるようにしてくれています。
- デザインパターンを組み合わせてコードを書こうとしないでください。がんばって自分の設計センス (= いろいろ見てきた経験) に従って書いているうちに、あるいは他人のコードを読んでいるうちに、そこにパターンを見出せるようになってください。それをコミュニケーションに活かしてください。
