---
date: 2024-01-26 04:39:32.350436-07:00
description: "\u8907\u7D20\u6570\u306B\u306F\u5B9F\u90E8\u3068\u865A\u90E8\uFF08`3\
  \ + 4i`\u306E\u3088\u3046\u306B\uFF09\u304C\u3042\u308A\u307E\u3059\u3002\u305D\u308C\
  \u3089\u306F\u3001\u5DE5\u5B66\u3001\u7269\u7406\u5B66\u3001\u304A\u3088\u3073\u7279\
  \u5B9A\u306E\u8A08\u7B97\u554F\u984C\u3067\u4F7F\u7528\u3055\u308C\u307E\u3059\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30B7\u30DF\u30E5\u30EC\u30FC\u30B7\
  \u30E7\u30F3\u3001\u4FE1\u53F7\u51E6\u7406\u3001\u304A\u3088\u3073\u7279\u5B9A\u306E\
  \u7A2E\u985E\u306E\u6570\u5B66\u554F\u984C\u3092\u52B9\u7387\u7684\u306B\u89E3\u6C7A\
  \u3059\u308B\u305F\u3081\u306B\u305D\u308C\u3089\u3092\u6271\u3044\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:41.604057-06:00'
model: gpt-4-0125-preview
summary: "\u8907\u7D20\u6570\u306B\u306F\u5B9F\u90E8\u3068\u865A\u90E8\uFF08`3 + 4i`\u306E\
  \u3088\u3046\u306B\uFF09\u304C\u3042\u308A\u307E\u3059\u3002\u305D\u308C\u3089\u306F\
  \u3001\u5DE5\u5B66\u3001\u7269\u7406\u5B66\u3001\u304A\u3088\u3073\u7279\u5B9A\u306E\
  \u8A08\u7B97\u554F\u984C\u3067\u4F7F\u7528\u3055\u308C\u307E\u3059\u3002\u30D7\u30ED\
  \u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30B7\u30DF\u30E5\u30EC\u30FC\u30B7\u30E7\u30F3\
  \u3001\u4FE1\u53F7\u51E6\u7406\u3001\u304A\u3088\u3073\u7279\u5B9A\u306E\u7A2E\u985E\
  \u306E\u6570\u5B66\u554F\u984C\u3092\u52B9\u7387\u7684\u306B\u89E3\u6C7A\u3059\u308B\
  \u305F\u3081\u306B\u305D\u308C\u3089\u3092\u6271\u3044\u307E\u3059\u3002."
title: "\u8907\u7D20\u6570\u306E\u6271\u3044\u65B9"
weight: 14
---

## どのようにして：
Elixirには組み込みの複素数がないため、自分で作成するか、`ComplexNum`のようなライブラリを使用します。ここでは、ライブラリを使用した簡単な例を紹介します：

```elixir
# ComplexNumがインストールされていると仮定
defmodule ComplexMath do
  import ComplexNum

  def add(a, b) do
    ComplexNum.add(a, b)
  end
end

# 複素数を作成してそれらを加算する
c1 = {3, 4}   # 3 + 4iを表す
c2 = {2, -3}  # 2 - 3iを表す
result = ComplexMath.add(c1, c2)
IO.puts "結果は：#{inspect(result)}"
```

この出力になります：
```
結果は：{5, 1}
```

これは、`3 + 4i`と`2 - 3i`の合計が`5 + 1i`であることを意味します。

## 深掘り
複素数は、マイナスの平方根を通常の数字では扱えなかったため、歴史の中で現れました。それらが真剣に受け止められたのは17世紀までなく、レネ・デカルトやジェロラモ・カルダノのような数学者のおかげでした。

Elixirでは、複素数には`{3, 4}`のようなタプルをよく使いますが、車輪の再発明を避けるために専用のライブを使用します。通常、ライブラリの方が優れています。これは、虚数単位'i'（FYI：`i`の二乗は`-1`に等しい）のためにトリッキーになる乗算や除算など、細かい点を処理します。

## 関連情報
これらのリソースもチェックしてみてください：
- ElixirのパッケージマネージャHex用の[ComplexNumライブラリ](https://hex.pm/packages/complex_num)。
- 高度なElixirのトピックや演習については、[Elixir School](https://elixirschool.com/en/)。
- Elixirが内部で使用するErlangの[mathモジュール](http://erlang.org/doc/man/math.html)、その他の数学的なニーズについて。
