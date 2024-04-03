---
date: 2024-01-26 01:11:54.593365-07:00
description: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B\u3053\
  \u3068\u306F\u3001\u5B9A\u7FA9\u3055\u308C\u305F\u76EE\u7684\u3092\u6301\u3064\u518D\
  \u5229\u7528\u53EF\u80FD\u306A\u30D6\u30ED\u30C3\u30AF\u306B\u30B3\u30FC\u30C9\u3092\
  \u5206\u5272\u3059\u308B\u3053\u3068\u306B\u3064\u3044\u3066\u3067\u3059\u3002\u79C1\
  \u305F\u3061\u306F\u3001\u7269\u4E8B\u3092\u6574\u9813\u3057\u3001\u5197\u9577\u6027\
  \u3092\u9632\u304E\u3001\u30C7\u30D0\u30C3\u30B0\u3092\u5BB9\u6613\u306B\u3059\u308B\
  \u305F\u3081\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:42.253247-06:00'
model: gpt-4-1106-preview
summary: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B\u3053\
  \u3068\u306F\u3001\u5B9A\u7FA9\u3055\u308C\u305F\u76EE\u7684\u3092\u6301\u3064\u518D\
  \u5229\u7528\u53EF\u80FD\u306A\u30D6\u30ED\u30C3\u30AF\u306B\u30B3\u30FC\u30C9\u3092\
  \u5206\u5272\u3059\u308B\u3053\u3068\u306B\u3064\u3044\u3066\u3067\u3059\u3002\u79C1\
  \u305F\u3061\u306F\u3001\u7269\u4E8B\u3092\u6574\u9813\u3057\u3001\u5197\u9577\u6027\
  \u3092\u9632\u304E\u3001\u30C7\u30D0\u30C3\u30B0\u3092\u5BB9\u6613\u306B\u3059\u308B\
  \u305F\u3081\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002."
title: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B"
weight: 18
---

## 方法：
ユーザーに挨拶するための繰り返しコードがあると想像してください。代わりに、`greet_user` のような関数でそれをラップしましょう：

```php
function greet_user($name) {
    return "Hello, " . $name . "!";
}

echo greet_user("Alice");
echo greet_user("Bob");
```

出力：
```
Hello, Alice!
Hello, Bob!
```

これで、挨拶したいときに毎回同じコード行を書き直さずに、いつでも使える便利なツールが手に入りました。

## 深掘り
関数はFORTRANの50年代初期からプログラミングにありました。それらは構造化プログラミングの基石であり、モジュール性と分離についてのものです。代替案ですか？クラスやメソッドについて話すオブジェクト指向に進むことができます。それらは、ファンシーなスーツを着た関数です。PHPについては、実装の詳細には、パラメータのデフォルト値の指定、入力の型ヒント、配列を使用するかPHP 7.1以降ではリストを使用して複数の値を返す機能が含まれます。

ここでは型宣言とデフォルト値が使われた現代的なひねりを見てみましょう：

```php
function add(float $a, float $b = 0.0): float {
    return $a + $b;
}

echo add(1.5);
echo add(1.5, 2.5);
```

PHP 7.4は、配列操作で一般的に使用される、簡潔なワンライナー関数を書くのに役立つアロー関数も導入しました：

```php
$numbers = array(1, 2, 3, 4);
$squared = array_map(fn($n) => $n * $n, $numbers);
print_r($squared);
```

出力：
```
Array
(
    [0] => 1
    [1] => 4
    [2] => 9
    [3] => 16
)
```

## 関連情報
- [関数についてのPHPマニュアル](https://www.php.net/manual/ja/functions.user-defined.php)
- [PHP: 正しい方法 - 関数](https://phptherightway.com/#functions)
- [PHP 7.4アロー関数について学ぶ](https://stitcher.io/blog/short-closures-in-php)
