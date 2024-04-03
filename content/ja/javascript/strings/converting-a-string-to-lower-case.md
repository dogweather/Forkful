---
date: 2024-01-20 17:38:47.081462-07:00
description: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\
  \u3068\u306F\u3001\u5168\u3066\u306E\u30A2\u30EB\u30D5\u30A1\u30D9\u30C3\u30C8\u6587\
  \u5B57\u3092\u5C0F\u6587\u5B57\u306B\u3059\u308B\u3053\u3068\u3067\u3059\u3002\u3053\
  \u306E\u64CD\u4F5C\u306F\u3001\u5927\u6587\u5B57\u3068\u5C0F\u6587\u5B57\u3092\u533A\
  \u5225\u3057\u306A\u3044\u6BD4\u8F03\u3092\u884C\u3063\u305F\u308A\u3001\u7D71\u4E00\
  \u7684\u306A\u30C7\u30FC\u30BF\u5F62\u5F0F\u3092\u4FDD\u3063\u305F\u308A\u3059\u308B\
  \u305F\u3081\u306B\u884C\u308F\u308C\u307E\u3059\u3002"
isCJKLanguage: true
lastmod: '2024-03-13T22:44:42.657676-06:00'
model: gpt-4-1106-preview
summary: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\
  \u3068\u306F\u3001\u5168\u3066\u306E\u30A2\u30EB\u30D5\u30A1\u30D9\u30C3\u30C8\u6587\
  \u5B57\u3092\u5C0F\u6587\u5B57\u306B\u3059\u308B\u3053\u3068\u3067\u3059\u3002\u3053\
  \u306E\u64CD\u4F5C\u306F\u3001\u5927\u6587\u5B57\u3068\u5C0F\u6587\u5B57\u3092\u533A\
  \u5225\u3057\u306A\u3044\u6BD4\u8F03\u3092\u884C\u3063\u305F\u308A\u3001\u7D71\u4E00\
  \u7684\u306A\u30C7\u30FC\u30BF\u5F62\u5F0F\u3092\u4FDD\u3063\u305F\u308A\u3059\u308B\
  \u305F\u3081\u306B\u884C\u308F\u308C\u307E\u3059\u3002."
title: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB"
weight: 4
---

## How to: (方法)
JavaScriptで文字列を小文字に変換するには、`toLowerCase()` メソッドを使います。以下はコード例と出力サンプルです。

```javascript
let greeting = "こんにちは、WORLD!";
let lowerCaseGreeting = greeting.toLowerCase();

console.log(lowerCaseGreeting); // "こんにちは、world!"
```

## Deep Dive (掘り下げ)
JavaScriptが最初に登場した頃から、文字列操作は基本的な機能の1つです。`toLowerCase()` メソッドは、ECMAScript標準の初期版において定義されており、今日に至るまで広く使われています。

代替手段として、正規表現と `replace()` メソッドを組み合わせることもできますが、これは非効率であり、単純な小文字変換には `toLowerCase()` の方が適しています。

小文字変換の実装はブラウザやJavaScriptエンジンによって異なりますが、Unicode標準に従い、さまざまな言語や特殊文字に対応していることが期待されます。

## See Also (関連情報)
- MDN Web Docsの `toLowerCase()` の解説: https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase
- ECMAScript標準の最新版: https://www.ecma-international.org/ecma-262/
