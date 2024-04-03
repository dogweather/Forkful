---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:49:09.460549-07:00
description: "\u5C06\u6765\u307E\u305F\u306F\u904E\u53BB\u306E\u65E5\u4ED8\u3092\u8A08\
  \u7B97\u3059\u308B\u3053\u3068\u306F\u3001\u305D\u308C\u305E\u308C\u73FE\u5728\u306E\
  \u65E5\u4ED8\u3092\u8D85\u3048\u308B\u304B\u3001\u307E\u305F\u306F\u305D\u308C\u4EE5\
  \u524D\u306E\u65E5\u4ED8\u3092\u898B\u3064\u3051\u308B\u305F\u3081\u306B\u65E5\u4ED8\
  \u30AA\u30D6\u30B8\u30A7\u30AF\u30C8\u3092\u64CD\u4F5C\u3059\u308B\u3053\u3068\u306B\
  \u3064\u3044\u3066\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\
  \u30EA\u30DE\u30A4\u30F3\u30C0\u30FC\u3084\u6709\u52B9\u671F\u9650\u306E\u8A2D\u5B9A\
  \u304B\u3089\u6642\u9593\u30D9\u30FC\u30B9\u306E\u30C7\u30FC\u30BF\u30C8\u30EC\u30F3\
  \u30C9\u306E\u5206\u6790\u307E\u3067\u3001\u3055\u307E\u3056\u307E\u306A\u30BF\u30B9\
  \u30AF\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:41.462225-06:00'
model: gpt-4-0125-preview
summary: "\u5C06\u6765\u307E\u305F\u306F\u904E\u53BB\u306E\u65E5\u4ED8\u3092\u8A08\
  \u7B97\u3059\u308B\u3053\u3068\u306F\u3001\u305D\u308C\u305E\u308C\u73FE\u5728\u306E\
  \u65E5\u4ED8\u3092\u8D85\u3048\u308B\u304B\u3001\u307E\u305F\u306F\u305D\u308C\u4EE5\
  \u524D\u306E\u65E5\u4ED8\u3092\u898B\u3064\u3051\u308B\u305F\u3081\u306B\u65E5\u4ED8\
  \u30AA\u30D6\u30B8\u30A7\u30AF\u30C8\u3092\u64CD\u4F5C\u3059\u308B\u3053\u3068\u306B\
  \u3064\u3044\u3066\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\
  \u30EA\u30DE\u30A4\u30F3\u30C0\u30FC\u3084\u6709\u52B9\u671F\u9650\u306E\u8A2D\u5B9A\
  \u304B\u3089\u6642\u9593\u30D9\u30FC\u30B9\u306E\u30C7\u30FC\u30BF\u30C8\u30EC\u30F3\
  \u30C9\u306E\u5206\u6790\u307E\u3067\u3001\u3055\u307E\u3056\u307E\u306A\u30BF\u30B9\
  \u30AF\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002."
title: "\u300C\u672A\u6765\u307E\u305F\u306F\u904E\u53BB\u306E\u65E5\u4ED8\u306E\u8A08\
  \u7B97\u300D"
weight: 26
---

## 方法：
Google Apps Scriptでは、JavaScriptに基づいて、`Date`オブジェクトを使用して日付を操作できます。将来および過去の日付を計算する方法は次のとおりです：

### 将来の日付計算
将来の日付を計算するには、現在の日付の日付オブジェクトを作成し、それに希望の日数（または他の時間単位）を追加します。

```javascript
// 現在の日付
var today = new Date();

// 将来の日付を10日後に計算
var futureDate = new Date(today);
futureDate.setDate(today.getDate() + 10);

Logger.log("将来の日付: " + futureDate.toDateString());
```

### 過去の日付計算
同様に、過去の日付を見つけるには、現在の日付から日数を引きます。

```javascript
// 現在の日付
var today = new Date();

// 過去の日付を10日前に計算
var pastDate = new Date(today);
pastDate.setDate(today.getDate() - 10);

Logger.log("過去の日付: " + pastDate.toDateString());
```

### サンプル出力
今日が2023年4月15日だと仮定すると、出力は次のようになります：

```
将来の日付: 火 4月 25 2023
過去の日付: 水 4月 5 2023
```

JavaScript（そしてGoogle Apps Script内で）の`Date`オブジェクトは、日付を追加または減算するときに自動的に月と年を調整することを覚えておいてください。

## ディープダイブ
`Date`オブジェクトを使用した日付の操作は、初期のJavaScriptの実装から始まります。時間が経つにつれて、このアプローチは一般的に一貫性が保たれ、開発者が外部ライブラリを必要とせずに日付を管理できる直接的な方法を提供してきました。しかし、タイムゾーンの調整や広範な日付ベースのデータを扱うようなより複雑な操作の場合、`Moment.js`やより現代的な`Luxon`のようなライブラリがより多くの機能と簡単な取り扱いを提供するかもしれません。

Google Apps Scriptにおいては、特に`Date`オブジェクトの直接的な利用可能性と単純さにもかかわらず、日付計算がスクリプトのパフォーマンスと実行時間にどのように影響を与えるかに注意することが重要です。特に、時間駆動のトリガーや広範なスプレッドシート操作でそうです。さらに、Google Apps Scriptはそのエコシステム内（Google SheetsやCalendarなど）で日付を扱うための組み込みメソッドを提供していますが、外部ライブラリの統合やGoogleのアドバンスドサービスの活用は、複雑なシナリオに対してより堅牢なソリューションを提供することがあります。

したがって、ネイティブのJavaScript `Date`オブジェクトの方法論が直接的な計算には通常十分であるとしても、外部ライブラリやサービスを探求することは、より微妙な要求に対する機能を強化することができます。
