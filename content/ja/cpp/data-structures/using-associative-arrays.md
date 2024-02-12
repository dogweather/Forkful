---
title:                "連想配列の使用"
aliases:
- ja/cpp/using-associative-arrays.md
date:                  2024-01-30T19:10:55.916591-07:00
model:                 gpt-4-0125-preview
simple_title:         "連想配列の使用"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/cpp/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 何となくなぜか？

C++ で `std::map` や `std::unordered_map` として知られている連想配列は、配列のインデックスと実世界のデータの間のギャップを埋めます。これにより、意味のあるキーを使用できます。キーを使用して高速に検索、挿入、削除が必要な場合には、これらが選ばれます。

## 方法:

C++ では、`<map>` と `<unordered_map>` のヘッダファイルとともに連想配列が使えるようになります。例を挙げながら、その使用方法を見てみましょう。

### `std::map` の使用

`std::map` はキーに基づいて要素をソートされた状態で保持します。使い始めるには以下のようにします：

```C++
#include <iostream>
#include <map>
#include <string>

int main() {
    std::map<std::string, int> ageMap;
    
    // 値の挿入
    ageMap["Alice"] = 30;
    ageMap["Bob"] = 25;
    
    // 値へのアクセス
    std::cout << "Bob の年齢: " << ageMap["Bob"] << std::endl;
    
    // map のイテレート
    for(const auto &pair : ageMap) {
        std::cout << pair.first << " の年齢は " << pair.second << " 歳です。" << std::endl;
    }
    
    return 0;
}
```

### `std::unordered_map` の使用

順序は関係なく、パフォーマンスが重要な場合は、`std::unordered_map` が便利です。挿入、検索、削除の平均的な複雑さで高速です。

```C++
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    std::unordered_map<std::string, double> productPrice;
    
    // 値の挿入
    productPrice["milk"] = 2.99;
    productPrice["bread"] = 1.99;
    
    // 値へのアクセス
    std::cout << "ミルクの価格: $" << productPrice["milk"] << std::endl;
    
    // unordered_map のイテレート
    for(const auto &pair : productPrice) {
        std::cout << pair.first << " のコストは $" << pair.second << " です。" << std::endl;
    }
    
    return 0;
}
```

## 深掘り

C++ での連想配列、特に `std::map` と `std::unordered_map` は、要素を保存するだけではありません。検索、挿入、削除といった操作を効果的な時間の複雑さ（`std::map` の場合は対数的、`std::unordered_map` の場合は平均的に定数時間）で可能にすることで、より複雑なデータ管理の基礎を提供します。この効率性は、`std::map` にはバランスのとれた木、`std::unordered_map` にはハッシュテーブルという、背後にあるデータ構造から来ています。

歴史的に、これらが標準ライブラリの一部となる前は、プログラマーは自分たちでバージョンを実装するか、サードパーティのライブラリを使用しなければならず、一貫性の欠如や潜在的な非効率性につながりました。C++ の標準ライブラリにマップが含まれたことで、その使用が標準化されただけでなく、異なるコンパイラーやプラットフォーム間でのパフォーマンスも最適化されました。

どちらも強力ではありますが、`std::map` と `std::unordered_map` の選択は、使用ケースの詳細にかかっています。順序付けられたデータが必要で、若干のパフォーマンスのトレードオフを気にしない場合は、`std::map` を選びます。スピードを求め、順序を気にしない場合は、`std::unordered_map` がおそらくより良い選択です。

しかし、複雑なデータ構造を扱う場合、常にトレードオフが存在することに注意が必要です。ニッチなケースでは、他のデータ構造やサードパーティのライブラリが、特定のニーズに合ったより良いパフォーマンスや機能を提供するかもしれません。プロジェクトの要件に基づいて常にオプションを考えてください。
