---
date: 2024-01-26 01:16:19.047883-07:00
description: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u5206\u5272\u3059\u308B\u3053\
  \u3068\u3067\u3001\u30B9\u30AF\u30EA\u30D7\u30C8\u3092\u518D\u5229\u7528\u53EF\u80FD\
  \u306A\u30C1\u30E3\u30F3\u30AF\u306B\u5206\u3051\u307E\u3059\u3002\u3053\u308C\u306F\
  \u3001\u30B3\u30FC\u30C9\u3092\u30AF\u30EA\u30FC\u30F3\u3067\u6271\u3044\u3084\u3059\
  \u304F\u3001\u30D0\u30B0\u306E\u5C11\u306A\u3044\u3082\u306E\u306B\u3059\u308B\u3053\
  \u3068\u306B\u3064\u3044\u3066\u3067\u3059\u3002\u30E2\u30B8\u30E5\u30E9\u30FC\u306A\
  \u30B3\u30FC\u30C9\u306F\u6642\u9593\u3092\u7BC0\u7D04\u3057\u3001\u7CBE\u795E\u7684\
  \u306A\u4F59\u88D5\u3092\u4FDD\u3061\u3001\u30C7\u30D0\u30C3\u30B0\u3084\u30E6\u30CB\
  \u30C3\u30C8\u30C6\u30B9\u30C8\u3092\u7C21\u7D20\u5316\u3059\u308B\u305F\u3081\u7D20\
  \u6674\u3089\u3057\u3044\u3082\u306E\u3067\u3059\u3002"
lastmod: '2024-03-13T22:44:42.862943-06:00'
model: gpt-4-0125-preview
summary: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u5206\u5272\u3059\u308B\u3053\
  \u3068\u3067\u3001\u30B9\u30AF\u30EA\u30D7\u30C8\u3092\u518D\u5229\u7528\u53EF\u80FD\
  \u306A\u30C1\u30E3\u30F3\u30AF\u306B\u5206\u3051\u307E\u3059\u3002\u3053\u308C\u306F\
  \u3001\u30B3\u30FC\u30C9\u3092\u30AF\u30EA\u30FC\u30F3\u3067\u6271\u3044\u3084\u3059\
  \u304F\u3001\u30D0\u30B0\u306E\u5C11\u306A\u3044\u3082\u306E\u306B\u3059\u308B\u3053\
  \u3068\u306B\u3064\u3044\u3066\u3067\u3059\u3002\u30E2\u30B8\u30E5\u30E9\u30FC\u306A\
  \u30B3\u30FC\u30C9\u306F\u6642\u9593\u3092\u7BC0\u7D04\u3057\u3001\u7CBE\u795E\u7684\
  \u306A\u4F59\u88D5\u3092\u4FDD\u3061\u3001\u30C7\u30D0\u30C3\u30B0\u3084\u30E6\u30CB\
  \u30C3\u30C8\u30C6\u30B9\u30C8\u3092\u7C21\u7D20\u5316\u3059\u308B\u305F\u3081\u7D20\
  \u6674\u3089\u3057\u3044\u3082\u306E\u3067\u3059\u3002."
title: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B"
weight: 18
---

## 方法：
ユーザーに挨拶する簡単なスクリプトを書いていると想像してみてください：

```Ruby
def greet(name)
  "Hello, #{name}!"
end

puts greet("Alice")   # 出力: Hello, Alice!
puts greet("Bob")     # 出力: Hello, Bob!
```

または、円の面積を計算しているかもしれません：

```Ruby
def circle_area(radius)
  Math::PI * radius ** 2
end

puts circle_area(5)   # 出力: 78.53981633974483
```

よりすっきりして扱いやすいですよね？

## 深堀り
関数の概念は、Rubyではメソッドとも呼ばれますが、新しいものではなく、プログラミング自体ほど古いです。1950年代にさかのぼると、冗長性を減らすために導入されたサブルーチンがありました。

代替手段？もちろん、インラインコードがありますし、クラスとオブジェクトでOOPにすることも、ラムダやprocsで関数型にすることもできます。しかし、関数は秩序あるコードの基本です。パフォーマンスが欲しいですか？関数内のローカル変数は速く、`return`で直ちに値を返すことができます。

実装面では、`def`で関数を定義し、`end`で終えます。デフォルトパラメータを設定したり、可変長関数のためにスプラットオペレータを使用したりなどができます。関数は、あなたの望むほどシンプルまたは複雑にすることができます。

## 関連項目
- [Rubyのメソッドドキュメント](https://ruby-doc.org/core-2.7.0/Method.html)
- [Learn to Program by Chris Pine](https://pine.fm/LearnToProgram/)
- [Practical Object-Oriented Design in Ruby by Sandi Metz](https://www.poodr.com/)
