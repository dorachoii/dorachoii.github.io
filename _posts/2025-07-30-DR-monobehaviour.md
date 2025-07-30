---
layout: post
title: "[オオバ]Unityの基礎ーMonoBehaviour徹底解説"
---

## 📖 今日の記事  
[【Unityの基礎】MonoBehaviour徹底解説](https://shibuya24.info/entry/unity-monobehaviour)

---

## 🗒️ 単語

| 単語        | 意味          | 文章                                        |
| --------- | ----------- | ----------------------------------------- |
| 肝(きも)     | 간           | Awake、Startメソッドといったイベント関数がMonoBehaviourの肝 |
| 外す(はずす)   | 떼다          |                                           |
| 被り(かぶり)   | 덮어쓰다        | 内容がすこし被ります。                               |
| 消耗(しょうもう) | 소모          | 細かい部分で消耗する                                |
| 枠内(わくない)  | 테두리 안, 범위 안 | 上図の枠内がコンパイルエラー。                           |
| 執筆(しっぴつ)  | 집필          | _記事を執筆_ しました。                             |


---

## 💡 インサイト

- MonoBehaviourの使用例
	- ①GameObjectにゲームの機能を追加
		- 画面に登場するオブジェクトに使用
		- MonoBehaviourを継承することで自作の機能を作れる
	- ②プログラミングの開始ポイント（イベント関数）
	- ③毎フレーム処理の実行

| イベント関数            | 특징 설명                                                                         |
| ----------------- | ----------------------------------------------------------------------------- |
| **① Awake()**     | - 最初に呼ばれる<br>- AwakeはMonoBehaviourがOFF（非アクティブ）の状態でも、GameObjectがON（アクティブ）ならで動作 |
| **② Start()**     | - Awakeから1フレーム遅れて実行<br>- GameObject、MonoBehaviourともにONの状態（アクティブ）で動作           |
| **③ OnEnable()**  | - Awakeの後に実行（Startよりも前）<br>- 何度も実行                                            |
| **④ OnDisable()** | - GameObjectまたはMonoBehaviourがOFFの状態で動作<br>- 何度も実行                             |
| **⑤ Update()**    | 毎フレーム実行                                                                       |
| **⑥ OnDestroy()** | - GameObjectまたはMonoBehaviourを削除すると動作                                          |
- 個人的に _初期化処理はStartではなくAwakeで実行するほうが安全_ という考えです。
- キャラクターやパズルのピースはGameObjectを使います。理由は _画面に表示する必要があり、さまざまな機能を実装するから_ です。
- Unityの数あるコンポーネントの中でMonoBehaviourは特殊。開発者が自作コンポーネントを作るために必須の機能です。