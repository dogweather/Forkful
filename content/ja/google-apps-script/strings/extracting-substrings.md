---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:53:03.739483-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:41.429200-06:00'
model: gpt-4-0125-preview
summary: "\u6587\u5B57\u5217\u306E\u62BD\u51FA\u306F\u3001\u6587\u5B57\u5217\u306E\
  \u4E00\u90E8\u3092\u53D6\u308A\u51FA\u3059\u3053\u3068\u3092\u610F\u5473\u3057\u307E\
  \u3059\u3002\u672C\u8CEA\u7684\u306B\u306F\u3001\u65E2\u5B58\u306E\u6587\u5B57\u5217\
  \u306E\u4E00\u90E8\u5206\u304B\u3089\u65B0\u3057\u3044\u6587\u5B57\u5217\u3092\u4F5C\
  \u6210\u3057\u3066\u3044\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\
  \u3001\u30C7\u30FC\u30BF\u306E\u89E3\u6790\u3001\u30E6\u30FC\u30B6\u30FC\u30A4\u30F3\
  \u30BF\u30FC\u30D5\u30A7\u30FC\u30B9\u306E\u30C6\u30AD\u30B9\u30C8\u64CD\u4F5C\u3001\
  \u3055\u307E\u3056\u307E\u306A\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u3078\
  \u306E\u5165\u529B\u51E6\u7406\u306A\u3069\u3001\u591A\u304F\u306E\u7406\u7531\u3067\
  \u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002\u3053\u308C\u306B\u3088\u308A\u3001\
  \u6587\u5B57\u5217\u306E\u62BD\u51FA\u306F\u3001\u3042\u3089\u3086\u308B\u30B9\u30AF\
  \u30EA\u30D7\u30C8\u30A2\u30FC\u30BB\u30CA\u30EB\u306E\u4E2D\u3067\u6C4E\u7528\u7684\
  \u306A\u30C4\u30FC\u30EB\u3068\u306A\u3063\u3066\u3044\u307E\u3059\u3002."
title: "\u90E8\u5206\u6587\u5B57\u5217\u306E\u62BD\u51FA"
weight: 6
---

## 方法：
Google Apps Scriptでは、現代のJavaScriptに基づいて、`substring()`、`substr()`、`slice()`を含むいくつかの方法を通じて、文字列の抽出が可能です。それぞれにニュアンスがありますが、指定された文字を文字列から引き出す目的をすべて果たします。

```javascript
// substring()を使用した例
var str = "Hello, world!";
var result = str.substring(0, 5);
console.log(result); // 出力：Hello

// substr()を使用した例
var resultSubstr = str.substr(7, 5);
console.log(resultSubstr); // 出力：world

// slice()を使用した例
var resultSlice = str.slice(-6);
console.log(resultSlice); // 出力：world!
```

各メソッドは2つの引数を取ります：開始位置と、`slice()`の場合は負のインデックスを受け入れることができますが、終了位置または抽出する文字の数です。これらの操作後に元の文字列が変更されないことに注意する価値があります。新しい文字列の値を返します。

## 詳細解説
歴史的に、文字列を抽出するためのJavaScriptメソッドは、類似した名前と機能により混乱の原因となっていました。しかし、Google Apps Scriptや現代のJavaScriptでは、`substring()`と`slice()`が最も頻繁に使用され、`substr()`は非推奨と見なされています。これは、将来的にも安全なコードを書くために重要です。

`substring()`と`slice()`の主な違いは、負のインデックスの扱い方にあります。`substring()`は負のインデックスを0として扱いますが、`slice()`は負のインデックスを受け入れ、文字列の末尾から抽出を開始することができます。これは、文字列の正確な長さがわからない場合や、末尾から抽出する必要がある場合に特に便利です。

文字列の抽出にどのメソッドを使用するかは、操作の具体的な要件（例えば、負のインデックスを扱うことが有益かどうかなど）や個人またはチームのコーディング標準によって決まることがよくあります。ベストプラクティスに一つの解答はありませんが、微妙な違いやパフォーマンスへの影響を理解することで、情報に基づいた決定を下すことができます。
