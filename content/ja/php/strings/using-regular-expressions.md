---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:55.001320-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:42.231395-06:00'
model: gpt-4-0125-preview
summary: "PHP\u306B\u304A\u3051\u308B\u6B63\u898F\u8868\u73FE\uFF08regex\uFF09\u306F\
  \u3001\u6587\u5B57\u5217\u5185\u306E\u6587\u5B57\u306E\u7D44\u307F\u5408\u308F\u305B\
  \u3092\u30DE\u30C3\u30C1\u3055\u305B\u308B\u305F\u3081\u306B\u4F7F\u7528\u3055\u308C\
  \u308B\u30D1\u30BF\u30FC\u30F3\u3067\u3042\u308A\u3001\u6D17\u7DF4\u3055\u308C\u305F\
  \u691C\u7D22\u30FB\u7F6E\u63DB\u64CD\u4F5C\u3084\u30C7\u30FC\u30BF\u691C\u8A3C\u3092\
  \u53EF\u80FD\u306B\u3057\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\
  \u3001\u30C6\u30AD\u30B9\u30C8\u89E3\u6790\u3001\u30D5\u30A9\u30FC\u30E0\u306E\u691C\
  \u8A3C\u3001\u307E\u305F\u306F\u30A6\u30A7\u30D6\u30C7\u30FC\u30BF\u306E\u30B9\u30AF\
  \u30EC\u30A4\u30D4\u30F3\u30B0\u306A\u3069\u306B\u304A\u3044\u3066\u3001\u305D\u306E\
  \u529B\u3068\u67D4\u8EDF\u6027\u3092\u6D3B\u7528\u3057\u3066\u3044\u307E\u3059\u3002\
  \u3053\u308C\u306B\u3088\u308A\u3001\u958B\u767A\u8005\u306E\u30C4\u30FC\u30EB\u30AD\
  \u30C3\u30C8\u306B\u304A\u3044\u3066\u6B20\u304B\u305B\u306A\u3044\u30C4\u30FC\u30EB\
  \u3068\u306A\u3063\u3066\u3044\u307E\u3059\u3002."
title: "\u6B63\u898F\u8868\u73FE\u306E\u4F7F\u7528"
weight: 11
---

## 使い方:
PHPはPCRE（Perlと互換性のある正規表現）ライブラリを通じて正規表現をサポートしており、豊富な関数セットを提供しています。以下がその使用方法です：

### パターンのマッチング:
文字列内にパターンが存在するかどうかを確認するには、`preg_match()`を使用します。この関数は、文字列内にパターンが見つかった場合は1を、見つからなかった場合は0を返します。

```php
if (preg_match("/\bweb\b/i", "PHPはウェブスクリプト言語です")) {
    echo "マッチが見つかりました。";
} else {
    echo "マッチが見つかりませんでした。";
}
// 出力: マッチが見つかりました。
```

### すべてのマッチを見つける:
`preg_match_all()`は、文字列内のパターンのすべての出現を見つける必要がある場合に使用されます。

```php
$text = "猫と犬";
$pattern = "/\b([a-z]+)\b/i";
preg_match_all($pattern, $text, $matches);
print_r($matches[0]);
// 出力: Array ( [0] => cats [1] => and [2] => dogs )
```

### テキストの置換:
正規表現にマッチするテキストを置き換えるには、`preg_replace()`が使用されます。これはデータのフォーマットやクリーニングに非常に強力です。

```php
$originalText = "2003年4月15日";
$pattern = "/(\w+) (\d+), (\d+)/i";
$replacement = '${1}1,$3';
echo preg_replace($pattern, $replacement, $originalText);
// 出力: 2003年4月1,15
```

### 文字列の分割:
`preg_split()`を使用して、デリミタとしてパターンを指定して文字列を配列に分割できます。

```php
$text = "PHPは、非常に人気のある、スクリプト言語です";
$parts = preg_split("/,\s*/", $text);
print_r($parts);
// 出力: Array ( [0] => PHPは [1] => 非常に人気のある [2] => スクリプト言語です )
```

さらに、複雑なregexパターンやタスクについては、Symfonyの`Finder`コンポーネントやLaravelのヘルパー関数のコレクションなどのフレームワークやライブラリがより便利な抽象化層を提供するかもしれません。しかし、PHPスクリプト内での効率的なテキスト処理や検証のためには、PHPの組み込みPCRE関数を理解して利用することが重要です。
