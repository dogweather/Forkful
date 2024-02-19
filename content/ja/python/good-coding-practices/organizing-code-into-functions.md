---
aliases:
- /ja/python/organizing-code-into-functions/
date: 2024-01-26 01:16:25.459420-07:00
description: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u307E\u3068\u3081\u308B\u3068\
  \u306F\u3001\u30B3\u30FC\u30C9\u3092\u7279\u5B9A\u306E\u76EE\u7684\u3092\u6301\u3063\
  \u305F\u518D\u5229\u7528\u53EF\u80FD\u306A\u30C1\u30E3\u30F3\u30AF\u306B\u5206\u89E3\
  \u3059\u308B\u3053\u3068\u3092\u6307\u3057\u307E\u3059\u3002\u305D\u308C\u3092\u884C\
  \u3046\u7406\u7531\u306F\u3001\u30B3\u30FC\u30C9\u3092\u3088\u308A\u30AF\u30EA\u30FC\
  \u30F3\u306B\u3057\u3001\u8AAD\u307F\u3084\u3059\u304F\u3001\u30C7\u30D0\u30C3\u30B0\
  \u3084\u66F4\u65B0\u3092\u5BB9\u6613\u306B\u3059\u308B\u305F\u3081\u3067\u3059\u3002"
lastmod: 2024-02-18 23:08:54.568924
model: gpt-4-0125-preview
summary: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u307E\u3068\u3081\u308B\u3068\
  \u306F\u3001\u30B3\u30FC\u30C9\u3092\u7279\u5B9A\u306E\u76EE\u7684\u3092\u6301\u3063\
  \u305F\u518D\u5229\u7528\u53EF\u80FD\u306A\u30C1\u30E3\u30F3\u30AF\u306B\u5206\u89E3\
  \u3059\u308B\u3053\u3068\u3092\u6307\u3057\u307E\u3059\u3002\u305D\u308C\u3092\u884C\
  \u3046\u7406\u7531\u306F\u3001\u30B3\u30FC\u30C9\u3092\u3088\u308A\u30AF\u30EA\u30FC\
  \u30F3\u306B\u3057\u3001\u8AAD\u307F\u3084\u3059\u304F\u3001\u30C7\u30D0\u30C3\u30B0\
  \u3084\u66F4\u65B0\u3092\u5BB9\u6613\u306B\u3059\u308B\u305F\u3081\u3067\u3059\u3002"
title: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B"
---

{{< edit_this_page >}}

## 何となぜ?
コードを関数にまとめるとは、コードを特定の目的を持った再利用可能なチャンクに分解することを指します。それを行う理由は、コードをよりクリーンにし、読みやすく、デバッグや更新を容易にするためです。

## 方法:
例えば、ある数の平方と立方を計算するスクリプトを書いているとしましょう。関数を使わないと、繰り返しの混乱に陥ります:

```Python
num = 4
square = num * num
cube = num * num * num
print(f"平方: {square}, 立方: {cube}")

num = 5
square = num * num
cube = num * num * num
print(f"平方: {square}, 立方: {cube}")
```
出力:
```
平方: 16, 立方: 64
平方: 25, 立方: 125
```

関数を使って整理すると、見た目がすっきりします:

```Python
def square(n):
    return n * n

def cube(n):
    return n ** 3

num = 4
print(f"平方: {square(num)}, 立方: {cube(num)}")

num = 5
print(f"平方: {square(num)}, 立方: {cube(num)}")
```
出力:
```
平方: 16, 立方: 64
平方: 25, 立方: 125
```

## 深掘り
昔のように、プログラムがシンプルだった時代には、指示リストを書くだけで済んだこともありました。しかし、ソフトウェアが複雑になるにつれて、開発者は同じコードを何度も何度も書き直していることに気付きました。ここで関数の出番です—単一のアクションを実行する再利用可能なコードブロックです。

関数の代替手段にはクラス（操作するデータと関数をまとめること）やインラインコード（必要なところで直接知識を、しかし複雑なタスクにはリスキー）があります。実装上のコツは、関数を作るだけでなく、それが一つのことをうまく行うようにすることです—単一責任の原則を思い出してください。理想的には、関数はステートレスであるべきです、つまり、入ってくるデータや出ていくデータに驚きがないことを意味します。

## 参照
- 公式Pythonチュートリアルの関数について: https://docs.python.org/3/tutorial/controlflow.html#defining-functions
- 'Clean Code' by Robert C. Martin, クリーンな関数の書き方に関する原則が述べられています。
- 'Refactoring: Improving the Design of Existing Code' by Martin Fowler, コードの整理の例が含まれています。
