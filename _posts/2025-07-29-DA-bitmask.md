---
layout: post
categories:
  - Algorithm
title: Paiza
---

## 🧩 問題概要

[Paiza-A062](https://paiza.jp/works/challenges/531)

- 入力：三つの2次原座標  
- 出力：反時計（１）、時計（ー１）、一直線（０）
---

## 🎯 難易度

- A rank

---

## 💡 解法ポイント

- bitmask

---

## 📝 レビュー

- **①　bitmaskですべての特徴組み合わせ**  
    　- 各マスクは「どの特徴を選ぶか」を表す
    
- **②　選ばれた特徴だけで `key` 生成**  
    
- **③　すべての key が重複しなければ、区別できる→`mask` に含まれる 1 の数数える**  
    　
![[KakaoTalk_20250729_130402461.jpg]]
---

## 💻 コード (C++)

### ✅ 正解VER.
```cpp
#include <iostream>
#include <vector>
#include <string>
#include <unordered_set>

using namespace std;

int main() {

    int N, L;
    cin >> N >> L;

    vector<vector<int>> ores(N, vector<int>(L));

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < L; j++) {
            cin >> ores[i][j];
        }
    }

    int answer = L;

    for (int mask = 1; mask < (1 << L); mask++) {

        unordered_set<string> seen;
        bool can_distinguish_all = true;
        
        for (int i = 0; i < N; i++) {
            string key = "";
            for (int bit = 0; bit < L; bit++) {
                if (mask & (1 << bit)) {
                    key += (ores[i][bit] + '0');
                }
            }

            if (seen.count(key)) {
                can_distinguish_all = false;
                break;
            }
            seen.insert(key);
        }  

        if (can_distinguish_all) {
            int bit_count = __builtin_popcount(mask);

            if (bit_count < answer) {
                answer = bit_count;
            }
        }
    }

    cout << answer << "\n";

    return 0;

}

```

