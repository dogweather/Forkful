---
date: 2024-01-26 04:45:43.132765-07:00
description: "\u8907\u7D20\u6570\u306B\u306F\u5B9F\u90E8\u3068\u865A\u90E8\u304C\u3042\
  \u308A\u3001\u30A8\u30F3\u30B8\u30CB\u30A2\u30EA\u30F3\u30B0\u3001\u7269\u7406\u5B66\
  \u3001\u30B3\u30F3\u30D4\u30E5\u30FC\u30BF\u30B0\u30E9\u30D5\u30A3\u30C3\u30AF\u30B9\
  \u306A\u3069\u69D8\u3005\u306A\u5206\u91CE\u3067\u4E0D\u53EF\u6B20\u3067\u3059\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u901A\u5E38\u306E\u5B9F\u6570\u3067\
  \u306F\u6271\u3048\u306A\u3044\u65B9\u7A0B\u5F0F\u3092\u89E3\u304F\u305F\u3081\u306B\
  \u305D\u308C\u3089\u3092\u4F7F\u7528\u3057\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:41.811531-06:00'
model: gpt-4-0125-preview
summary: "\u8907\u7D20\u6570\u306B\u306F\u5B9F\u90E8\u3068\u865A\u90E8\u304C\u3042\
  \u308A\u3001\u30A8\u30F3\u30B8\u30CB\u30A2\u30EA\u30F3\u30B0\u3001\u7269\u7406\u5B66\
  \u3001\u30B3\u30F3\u30D4\u30E5\u30FC\u30BF\u30B0\u30E9\u30D5\u30A3\u30C3\u30AF\u30B9\
  \u306A\u3069\u69D8\u3005\u306A\u5206\u91CE\u3067\u4E0D\u53EF\u6B20\u3067\u3059\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u901A\u5E38\u306E\u5B9F\u6570\u3067\
  \u306F\u6271\u3048\u306A\u3044\u65B9\u7A0B\u5F0F\u3092\u89E3\u304F\u305F\u3081\u306B\
  \u305D\u308C\u3089\u3092\u4F7F\u7528\u3057\u307E\u3059\u3002."
title: "\u8907\u7D20\u6570\u306E\u6271\u3044\u65B9"
weight: 14
---

## 使い方：
Rustには複素数をサポートする組み込み機能はありませんが、`num-complex`のようなクレートがサポートしてくれます。使い方は以下のとおりです：

```rust
use num_complex::Complex;

fn main() {
    let a = Complex::new(2.0, 3.0); // 2 + 3i
    let b = Complex::new(1.0, -4.0); // 1 - 4i

    let sum = a + b;
    let product = a * b;

    println!("Sum: {}", sum); // 合計: 3 - 1i
    println!("Product: {}", product); // 積: 14 - 5i
}
```
このマジックを実現するためには、`Cargo.toml`に`num_complex`を追加する必要があります。

## 深掘り
複素数は16世紀に考案されましたが、18世紀に入り、オイラーのような数学者がそれらを取り扱い始めたときに本当に隆盛を迎えました。

ネイティブの複素数操作をサポートしていない言語は、Rustのようにサードパーティーのライブラリに依存します。`num-complex`はそのようなクレートの一つであり、Rustに数値型とトレイトを提供することを目指す`num`クレートコレクションの一部です。

複素数を組み込みサポートしている言語（Pythonなど）や、標準ライブラリの一部として提供している言語（`<complex>`ヘッダーを持つC++など）がある一方で、Rustでは標準ライブラリを小さく保つという決定により、追加機能のためにコミュニティが作成したクレートに頻繁に頼ることになります。

## 参照
- [Rustの本](https://doc.rust-lang.org/book/): Rustと外部クレートの使用方法をさらに学ぶには。
- [複素数Wikipedia](https://en.wikipedia.org/wiki/Complex_number): 複素数についてより深く理解するために。
