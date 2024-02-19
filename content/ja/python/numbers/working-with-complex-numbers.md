---
aliases:
- /ja/python/working-with-complex-numbers/
date: 2024-01-26 04:45:05.245915-07:00
description: "\u8907\u7D20\u6570\u306F`a + bi`\u306E\u5F62\u306E\u6570\u306E\u96C6\
  \u5408\u3067\u3042\u308A\u3001\u3053\u3053\u3067`a`\u3068`b`\u306F\u5B9F\u6570\u3067\
  \u3042\u308A\u3001`i`\u306F\u865A\u6570\u5358\u4F4D\uFF08`i^2 = -1`\uFF09\u3067\u3059\
  \u3002\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u3067\u306F\u3001\u96FB\u6C17\u5DE5\
  \u5B66\u3001\u4FE1\u53F7\u51E6\u7406\u3001\u91CF\u5B50\u30B3\u30F3\u30D4\u30E5\u30FC\
  \u30C6\u30A3\u30F3\u30B0\u306A\u3069\u3001\u3055\u307E\u3056\u307E\u306A\u9818\u57DF\
  \u306E\u554F\u984C\u3092\u89E3\u6C7A\u3059\u308B\u305F\u3081\u306B\u305D\u308C\u3089\
  \u3092\u4F7F\u7528\u3057\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:54.558231
model: gpt-4-0125-preview
summary: "\u8907\u7D20\u6570\u306F`a + bi`\u306E\u5F62\u306E\u6570\u306E\u96C6\u5408\
  \u3067\u3042\u308A\u3001\u3053\u3053\u3067`a`\u3068`b`\u306F\u5B9F\u6570\u3067\u3042\
  \u308A\u3001`i`\u306F\u865A\u6570\u5358\u4F4D\uFF08`i^2 = -1`\uFF09\u3067\u3059\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u3067\u306F\u3001\u96FB\u6C17\u5DE5\u5B66\
  \u3001\u4FE1\u53F7\u51E6\u7406\u3001\u91CF\u5B50\u30B3\u30F3\u30D4\u30E5\u30FC\u30C6\
  \u30A3\u30F3\u30B0\u306A\u3069\u3001\u3055\u307E\u3056\u307E\u306A\u9818\u57DF\u306E\
  \u554F\u984C\u3092\u89E3\u6C7A\u3059\u308B\u305F\u3081\u306B\u305D\u308C\u3089\u3092\
  \u4F7F\u7528\u3057\u307E\u3059\u3002"
title: "\u8907\u7D20\u6570\u306E\u6271\u3044\u65B9"
---

{{< edit_this_page >}}

## 何となぜ？
複素数は`a + bi`の形の数の集合であり、ここで`a`と`b`は実数であり、`i`は虚数単位（`i^2 = -1`）です。プログラミングでは、電気工学、信号処理、量子コンピューティングなど、さまざまな領域の問題を解決するためにそれらを使用します。

## 使い方：
Pythonには複素数をサポートするための組込みの機能があります。ここでは、それらをどのように扱うかを示します：

```Python
# 複素数の生成
z = 4 + 5j
print(z)  # 出力: (4+5j)

# 実部と虚部へのアクセス
print(z.real)  # 出力: 4.0
print(z.imag)  # 出力: 5.0

# 複素数の算術
w = 1 - 2j
print(z + w)  # 出力: (5+3j)
print(z - w)  # 出力: (3+7j)
print(z * w)  # 出力: (14+2j)
print(z / w)  # 出力: (-3.6+1.2j)

# 絶対値（モジュラス）
print(abs(z))  # 出力: 6.4031242374328485

# 複素数の共役
print(z.conjugate())  # 出力: (4-5j)
```

## ディープダイブ
複素数は、16世紀にジェロラモ・カルダノによって初めて概念化されました。Pythonをはじめとする他のプログラミング言語では、複素数を第一級の市民として扱います。これは、それらが言語に組み込まれており、基本操作のために外部ライブラリをインポートする必要がない、簡単に使える特徴を持っていることを意味します。

しかし、重い数値計算には、`cmath`というライブラリがPythonにはあります。これは複素数専用で、`exp`、`log`、三角関数の操作などの追加機能があります。

Pythonだけでは不十分な場合、特に複素数を含む配列操作には、NumPyを使うことがあります。NumPyは、数値計算のパフォーマンスに欠かせない最適化されたベクトル演算を提供します。

## 参照
もっと学びたい方は、これらのリソースをチェックしてください：

- 複素数に関するPythonの公式ドキュメント: https://docs.python.org/3/library/stdtypes.html#typesnumeric
- `cmath`モジュールのドキュメント: https://docs.python.org/3/library/cmath.html
- 複素数の配列を扱うNumPy: https://numpy.org/doc/stable/user/absolute_beginners.html#the-basics
