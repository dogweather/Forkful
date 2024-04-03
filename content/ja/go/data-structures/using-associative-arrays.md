---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:11:05.988553-07:00
description: "\u9023\u60F3\u914D\u5217\u306F\u3001Go\u3067\u306F\u30DE\u30C3\u30D7\
  \u3068\u3057\u3066\u77E5\u3089\u308C\u3066\u304A\u308A\u3001\u5404\u30E6\u30CB\u30FC\
  \u30AF\u30AD\u30FC\u304C\u5024\u306B\u30DE\u30C3\u30D7\u3059\u308B\u5834\u6240\u306B\
  \u30AD\u30FC\u5024\u30DA\u30A2\u3092\u4FDD\u5B58\u3067\u304D\u307E\u3059\u3002\u30D7\
  \u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u52B9\u7387\u7684\u306A\u30C7\u30FC\u30BF\
  \u306E\u691C\u7D22\u3001\u4FEE\u6B63\u3001\u305D\u3057\u3066\u72EC\u81EA\u306E\u30AD\
  \u30FC\u3092\u4F7F\u3063\u3066\u901F\u304F\u30A2\u30AF\u30BB\u30B9\u3067\u304D\u308B\
  \u8981\u7D20\u306E\u30B3\u30EC\u30AF\u30B7\u30E7\u30F3\u3092\u7DAD\u6301\u3059\u308B\
  \u305F\u3081\u306B\u30DE\u30C3\u30D7\u3092\u4F7F\u7528\u3057\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:41.375152-06:00'
model: gpt-4-0125-preview
summary: "\u9023\u60F3\u914D\u5217\u306F\u3001Go\u3067\u306F\u30DE\u30C3\u30D7\u3068\
  \u3057\u3066\u77E5\u3089\u308C\u3066\u304A\u308A\u3001\u5404\u30E6\u30CB\u30FC\u30AF\
  \u30AD\u30FC\u304C\u5024\u306B\u30DE\u30C3\u30D7\u3059\u308B\u5834\u6240\u306B\u30AD\
  \u30FC\u5024\u30DA\u30A2\u3092\u4FDD\u5B58\u3067\u304D\u307E\u3059\u3002\u30D7\u30ED\
  \u30B0\u30E9\u30DE\u30FC\u306F\u3001\u52B9\u7387\u7684\u306A\u30C7\u30FC\u30BF\u306E\
  \u691C\u7D22\u3001\u4FEE\u6B63\u3001\u305D\u3057\u3066\u72EC\u81EA\u306E\u30AD\u30FC\
  \u3092\u4F7F\u3063\u3066\u901F\u304F\u30A2\u30AF\u30BB\u30B9\u3067\u304D\u308B\u8981\
  \u7D20\u306E\u30B3\u30EC\u30AF\u30B7\u30E7\u30F3\u3092\u7DAD\u6301\u3059\u308B\u305F\
  \u3081\u306B\u30DE\u30C3\u30D7\u3092\u4F7F\u7528\u3057\u307E\u3059\u3002."
title: "\u9023\u60F3\u914D\u5217\u306E\u4F7F\u7528"
weight: 15
---

## 使い方:
Goでマップを作成して初期化する方法はいくつかあります。始めるための基本的な例をここに示します:

```go
package main

import "fmt"

func main() {
    // マップの宣言と初期化
    colors := map[string]string{
        "red":   "#FF0000",
        "green": "#00FF00",
        "blue":  "#0000FF",
    }

    fmt.Println(colors)
    // 出力: map[blue:#0000FF green:#00FF00 red:#FF0000]
}
```

要素を追加または更新するには、以下のようにキーに値を割り当てます:

```go
colors["white"] = "#FFFFFF"
fmt.Println(colors)
// 出力: map[blue:#0000FF green:#00FF00 red:#FF0000 white:#FFFFFF]
```

キーで値にアクセスするのは簡単です:

```go
fmt.Println("The hex code for red is:", colors["red"])
// 出力: The hex code for red is: #FF0000
```

要素を削除するには、`delete`関数を使用します:

```go
delete(colors, "red")
fmt.Println(colors)
// 出力: map[blue:#0000FF green:#00FF00 white:#FFFFFF]
```

マップを反復処理するには、forループを使用します:

```go
for color, hex := range colors {
    fmt.Printf("Key: %s Value: %s\n", color, hex)
}
```

Goのマップは順不同であることを覚えておいてください。反復の順序は保証されません。

## 深堀り
Goでは、マップはハッシュテーブルとして実装されています。マップの各エントリには2つの項目が含まれています：キーと値。エントリはキーをハッシュして保存されます。これにより、小さなデータセットの場合は定数時間の操作が可能であり、適切なハッシュ化が行われた場合の平均時間の複雑さはO(1)となりますが、多くのハッシュ衝突が発生する最悪の場合にはO(n)に劣化する可能性があります。

新しいGoプログラマーにとって重要な注記は、マップタイプが参照タイプであるということです。これは、関数にマップを渡すと、その関数内でマップに行われた変更が呼び出し元に対して可視であることを意味します。これは、例えば、構造体を関数に渡す場合と異なります。その場合、構造体はポインタによって渡されない限りコピーされます。

マップは連想配列を扱う場合には非常に多目的で効率的ですが、パフォーマンスが重要なアプリケーションでは、キーの分布が頻繁な衝突を引き起こす可能性がある場合、特に予測可能なパフォーマンス特性を持つデータ構造を使用することが有益かもしれません。

また、Go 1.9 以降で利用可能な`sync.Map`も検討する代替手段の一つです。これは、キーが一度書き込まれるが多くの回読み込まれる場合に使用されることを目的としており、これらのシナリオでの効率改善を提供します。しかし、一般的なGoアプリケーションにおいては、そのシンプルさと言語での直接サポートにより、通常のマップの使用が慣用的であり、推奨されるアプローチであることが多いです。
