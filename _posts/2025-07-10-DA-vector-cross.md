---
layout: post
title: "[BOJ] CCW"
date: 2025-07-10 13:56:00 +0900
categories:
  - Algorithm
tags:
  - vector
toc:
---
## 🧩 問題概要

[BOJ-11758](https://www.acmicpc.net/problem/11758)

- 入力：三つの2次原座標  
- 出力：反時計（１）、時計（ー１）、一直線（０）
---

## 🎯 難易度

- Gold 5

---

## 💡 解法ポイント

- float 割り算
- Vector Cross（ベクトル内積）

---

## 📝 レビュー

### 1) 最初の方法

最初の傾きを基準にして、次の傾きがそれより大きければ反時計回り、小さければ時計回りと判定しようとした。

-　`float`による割り算は予期しない結果を生む可能性
-　分母が0になる可能性

---

### 2) ベクトルの外積
외적은 두 벡터가 만드는 평행사변형의 넓이와 방향(부호)

여기 다시 보기!

---

## 💻 コード (C++)

### ❌ 不正解VER.

```cpp
#include <iostream>
#include <string>
#include <vector>

using namespace std;

int main() {
    vector<pair<int, int>> points;
    int x, y;

    for(int i = 0; i < 3; i++){
        cin >> x >> y;
        points.push_back({x,y});
    }  

    float dx1 = points[1].first - points[0].first;
    float dy1 = points[1].second - points[0].second;

    float dx2 = points[2].first - points[1].first;
    float dy2 = points[2].second - points[1].second;

    if(dy1/dx1 == dy2/dx2) cout << 0 << endl;
    if(dy1/dx1 < dy2/dx2) cout << 1 << endl;
    if(dy1/dx1 > dy2/dx2) cout << -1 << endl;

    return 0;
}
```
### ✅ 正解VER.
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<pair<int, int>> points;
    int x, y;

    for(int i = 0; i < 3; i++){
        cin >> x >> y;
        points.push_back({x, y});
    }

    int dx1 = points[1].first - points[0].first;
    int dy1 = points[1].second - points[0].second;

    int dx2 = points[2].first - points[1].first;
    int dy2 = points[2].second - points[1].second;

    int cross = dx1 * dy2 - dy1 * dx2;

    if (cross == 0) cout << 0 << endl;     // 직선
    else if (cross > 0) cout << 1 << endl; // 반시계 방향
    else cout << -1 << endl;               // 시계 방향

    return 0;
}

```

