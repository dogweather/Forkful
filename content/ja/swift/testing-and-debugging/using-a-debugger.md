---
date: 2024-01-26 04:10:56.786043-07:00
description: "\u30C7\u30D0\u30C3\u30AC\u3092\u4F7F\u7528\u3059\u308B\u3068\u3044\u3046\
  \u3053\u3068\u306F\u3001\u5B9F\u884C\u4E2D\u306E\u30B3\u30FC\u30C9\u3092\u30C6\u30B9\
  \u30C8\u3057\u3001\u691C\u67FB\u3059\u308B\u305F\u3081\u306E\u7279\u6B8A\u306A\u30C4\
  \u30FC\u30EB\u3092\u6D3B\u7528\u3059\u308B\u3053\u3068\u3092\u610F\u5473\u3057\u307E\
  \u3059\u3002\u3053\u308C\u306F\u5927\u304D\u306A\u610F\u5473\u304C\u3042\u308A\u307E\
  \u3059\u3002\u306A\u305C\u306A\u3089\u3001\u30D7\u30ED\u30B0\u30E9\u30E0\u306E\u5185\
  \u90E8\u3067\u4F55\u304C\u8D77\u3053\u3063\u3066\u3044\u308B\u304B\u3092\u898B\u308B\
  \u3053\u3068\u304C\u3067\u304D\u3001\u30D0\u30B0\u3092\u898B\u3064\u3051\u3001\u30B3\
  \u30FC\u30C9\u306E\u52D5\u4F5C\u3092\u3088\u308A\u3088\u304F\u7406\u89E3\u3067\u304D\
  \u308B\u304B\u3089\u3067\u3059\u3002"
lastmod: '2024-03-13T22:44:42.620340-06:00'
model: gpt-4-0125-preview
summary: "\u30C7\u30D0\u30C3\u30AC\u3092\u4F7F\u7528\u3059\u308B\u3068\u3044\u3046\
  \u3053\u3068\u306F\u3001\u5B9F\u884C\u4E2D\u306E\u30B3\u30FC\u30C9\u3092\u30C6\u30B9\
  \u30C8\u3057\u3001\u691C\u67FB\u3059\u308B\u305F\u3081\u306E\u7279\u6B8A\u306A\u30C4\
  \u30FC\u30EB\u3092\u6D3B\u7528\u3059\u308B\u3053\u3068\u3092\u610F\u5473\u3057\u307E\
  \u3059\u3002\u3053\u308C\u306F\u5927\u304D\u306A\u610F\u5473\u304C\u3042\u308A\u307E\
  \u3059\u3002\u306A\u305C\u306A\u3089\u3001\u30D7\u30ED\u30B0\u30E9\u30E0\u306E\u5185\
  \u90E8\u3067\u4F55\u304C\u8D77\u3053\u3063\u3066\u3044\u308B\u304B\u3092\u898B\u308B\
  \u3053\u3068\u304C\u3067\u304D\u3001\u30D0\u30B0\u3092\u898B\u3064\u3051\u3001\u30B3\
  \u30FC\u30C9\u306E\u52D5\u4F5C\u3092\u3088\u308A\u3088\u304F\u7406\u89E3\u3067\u304D\
  \u308B\u304B\u3089\u3067\u3059\u3002"
title: "\u30C7\u30D0\u30C3\u30AC\u30FC\u306E\u4F7F\u3044\u65B9"
---

## 使い方：
SwiftのIDEであるXcodeでデバッガを使用するには、ブレークポイントを設定し、変数を調べ、式を監視できます。例を見てみましょう：

```Swift
func findFactorial(of number: Int) -> Int {
    if number == 0 {
        return 1
    }
    return number * findFactorial(of: number - 1)
}

let result = findFactorial(of: 5)
print(result)
```

Xcodeで行番号の左をクリックしてブレークポイントを設定し、プログラムを実行します。ブレークポイントに到達すると、Xcodeは実行を一時停止します。これで以下を行うことができます：

1. 変数の値をチェックする。
2. デバッガのコントロールを使用して、次の行を実行（ステップオーバー）するか、関数内に入る（ステップイン）。
3. 特定の変数や定数の変更を監視するために「監視リスト」に式を追加する。

デバッグ領域で以下のようなことが見られるかもしれません：

```
(lldb) po number
5
(lldb) po result
120
```

## 深掘り：
デバッガは、1940年代からプログラミングの風景の一部となっており、単純なブレークポイントシステムから複雑なUI操作体験まで進化してきました。Xcodeの組み込みデバッガ以外の選択肢には、Xcodeが内部で使用しているLLDB（Low Level Debugger）のようなサードパーティツールが含まれます。一部の人々は、`print()`ステートメントを使用してデバッグを行います（俗に「洞窟人デバッギング」と呼ばれますが）、これは大規模なプロジェクトや複雑なバグには効率的ではありません。デバッガを使用するとき、実行制御、ランタイムの内省、およびデータ操作を扱っています。これらの原則を深く理解することは、効率的なデバッグに大きく寄与します。

## 参照：
- [AppleのXcodeデバッグガイド](https://developer.apple.com/documentation/xcode/debugging/)
- [LLDBクイックスタートガイド](https://lldb.llvm.org/use/tutorial.html)
- [Ray WenderlichのSwiftデバッグチュートリアル](https://www.raywenderlich.com/966538-arc-and-memory-management-in-swift)
