---
date: 2024-01-26 04:40:08.857339-07:00
description: "\u8907\u7D20\u6570\u306F\u5B9F\u6570\u3068\u865A\u6570\u306E\u7D44\u307F\
  \u5408\u308F\u305B\u3067\u3001`a + bi` \u306E\u3088\u3046\u306B\u8868\u3055\u308C\
  \u307E\u3059\u3002\u3053\u3053\u3067 `i` \u306F -1 \u306E\u5E73\u65B9\u6839\u3067\
  \u3059\u3002\u8907\u7D20\u6570\u306F\u3001\u901A\u5E38\u306E\u6570\u3067\u306F\u89E3\
  \u3051\u306A\u3044\u554F\u984C\u3092\u89E3\u6C7A\u3059\u308B\u305F\u3081\u306B\u3001\
  \u5DE5\u5B66\u3084\u7269\u7406\u5B66\u306A\u3069\u306E\u5206\u91CE\u3067\u91CD\u8981\
  \u3067\u3059\u3002"
lastmod: '2024-03-13T22:44:41.999865-06:00'
model: gpt-4-0125-preview
summary: "\u8907\u7D20\u6570\u306F\u5B9F\u6570\u3068\u865A\u6570\u306E\u7D44\u307F\
  \u5408\u308F\u305B\u3067\u3001`a + bi` \u306E\u3088\u3046\u306B\u8868\u3055\u308C\
  \u307E\u3059\u3002\u3053\u3053\u3067 `i` \u306F -1 \u306E\u5E73\u65B9\u6839\u3067\
  \u3059\u3002\u8907\u7D20\u6570\u306F\u3001\u901A\u5E38\u306E\u6570\u3067\u306F\u89E3\
  \u3051\u306A\u3044\u554F\u984C\u3092\u89E3\u6C7A\u3059\u308B\u305F\u3081\u306B\u3001\
  \u5DE5\u5B66\u3084\u7269\u7406\u5B66\u306A\u3069\u306E\u5206\u91CE\u3067\u91CD\u8981\
  \u3067\u3059\u3002."
title: "\u8907\u7D20\u6570\u306E\u6271\u3044\u65B9"
weight: 14
---

## 方法：
Elmは複素数をサポートしていませんので、自分の型と関数を作成します。以下は簡単な設定です：

```Elm
type alias Complex =
    { real : Float, imaginary : Float }

add : Complex -> Complex -> Complex
add a b =
    { real = a.real + b.real, imaginary = a.imaginary + b.imaginary }

-- 例：
a = { real = 3, imaginary = 2 }
b = { real = 1, imaginary = -4 }

sum = add a b
-- sum は { real = 4.0, imaginary = -2.0 }
```

## 掘り下げ
歴史的に、複素数は常に受け入れられていたわけではありません。16世紀になって、立方方程式を解くためのゲームチェンジャーとなりました。Pythonなど他の言語では、箱から出してすぐに使える複素数サポートと演算を提供しています。ご覧の通り、ElmではDIYのアプローチが必要です。しかし、掛け算、割り算、その他の演算を構築し、パフォーマンスの問題を調整することで、必要なほど洗練されたものにすることができます。

## 参照
- Elmの公式ドキュメント：https://package.elm-lang.org/ カスタムタイプの作成とElmの基本をマスターするために。
- 数学史に興味がある方は、Paul J. Nahin著の「An Imaginary Tale」で、複素数が時間を通じてどのように進化したかをチェックしてみてください。
- 複素数の魔術を活かす数学指向のプログラミングチャレンジには、プロジェクトオイラー（https://projecteuler.net）に挑戦してみてください。
