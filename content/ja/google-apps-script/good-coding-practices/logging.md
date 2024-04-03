---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:56:17.369578-07:00
description: "\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u306B\u304A\u3051\u308B\u30ED\
  \u30AE\u30F3\u30B0\u3068\u306F\u3001\u5B9F\u884C\u6642\u306E\u30A4\u30D9\u30F3\u30C8\
  \u3001\u30A8\u30E9\u30FC\u3001\u307E\u305F\u306F\u6CE8\u76EE\u3059\u3079\u304D\u767A\
  \u751F\u3092\u8A18\u9332\u3059\u308B\u3053\u3068\u3092\u6307\u3057\u307E\u3059\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u554F\u984C\u306E\u30C7\u30D0\u30C3\
  \u30B0\u3001\u30D1\u30D5\u30A9\u30FC\u30DE\u30F3\u30B9\u306E\u76E3\u8996\u3001\u304A\
  \u3088\u3073\u904B\u7528\u30C7\u30FC\u30BF\u306E\u8A18\u9332\u3092\u884C\u3046\u305F\
  \u3081\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002\u3053\u308C\u306F\u3001\
  \u672C\u756A\u74B0\u5883\u306E\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\u306E\u52D5\u4F5C\
  \u3092\u7DAD\u6301\u3057\u7406\u89E3\u3059\u308B\u305F\u3081\u306B\u91CD\u8981\u3067\
  \u3059\u3002"
lastmod: '2024-03-13T22:44:41.454667-06:00'
model: gpt-4-0125-preview
summary: "\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u306B\u304A\u3051\u308B\u30ED\
  \u30AE\u30F3\u30B0\u3068\u306F\u3001\u5B9F\u884C\u6642\u306E\u30A4\u30D9\u30F3\u30C8\
  \u3001\u30A8\u30E9\u30FC\u3001\u307E\u305F\u306F\u6CE8\u76EE\u3059\u3079\u304D\u767A\
  \u751F\u3092\u8A18\u9332\u3059\u308B\u3053\u3068\u3092\u6307\u3057\u307E\u3059\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u554F\u984C\u306E\u30C7\u30D0\u30C3\
  \u30B0\u3001\u30D1\u30D5\u30A9\u30FC\u30DE\u30F3\u30B9\u306E\u76E3\u8996\u3001\u304A\
  \u3088\u3073\u904B\u7528\u30C7\u30FC\u30BF\u306E\u8A18\u9332\u3092\u884C\u3046\u305F\
  \u3081\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002\u3053\u308C\u306F\u3001\
  \u672C\u756A\u74B0\u5883\u306E\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\u306E\u52D5\u4F5C\
  \u3092\u7DAD\u6301\u3057\u7406\u89E3\u3059\u308B\u305F\u3081\u306B\u91CD\u8981\u3067\
  \u3059\u3002."
title: "\u30ED\u30AE\u30F3\u30B0"
weight: 17
---

## 方法:
Google Apps Scriptでは、`Logger` クラスや `console.log()` など、さまざまな方法を使用してロギングを実行できます。Logger クラスは伝統的な方法であり、シンプルなデバッグや開発目的に適しています。最近のアップデートでは、`console.log()` は Stackdriver ロギングとの統合と柔軟性を提供し、Google Cloud PlatformでのApps Scriptsの監視により堅牢なソリューションを提供します。

**Logger の使用:**

```javascript
function logSample() {
  Logger.log('これはシンプルなログメッセージです');
  
  var value = 5;
  Logger.log('値は: %s', value); // 文字列のフォーマッティング
}

// ログを表示するには:
// 1. logSample関数を実行します。
// 2. 表示 -> ログ
```

**Loggerのサンプル出力:**

```
[22-04-20 10:00:00:000 PDT] これはシンプルなログメッセージです
[22-04-20 10:00:00:001 PDT] 値は: 5
```

**console.log() の使用:**

```javascript
function consoleLogSample() {
  console.log('このメッセージはStackdriver Loggingに送られます');
  const obj = {name: 'Jane', role: 'Developer'};
  console.info('オブジェクトをログに記録:', obj);
}

// ログはGoogle Cloud Platform (GCP) のコンソールで Stackdriver Loggingの下で見ることができます。
```

**console.log()のサンプル出力:**

```
このメッセージはStackdriver Loggingに送られます
オブジェクトをログに記録: {name: "Jane", role: "Developer"}
```

`console.log()` への移行により、開発者はGCPによって提供される強力なフィルターやツールを使用して、ログを効率的に解析し分析することができ、これは伝統的なLoggerクラスでは直感的ではありません。

## 詳細な解説:
Google Apps Scriptのロギングは、大きく進化しました。初期には、`Logger` クラスが開発者がスクリプトをデバッグするための主要な方法でした。これはシンプルで、基本的なスクリプトには十分ですが、ログの検索や時間の経過によるログトレンドの分析など、現代のクラウドアプリケーションに必要な機能には欠けています。

`console.log()` の導入により、このギャップが埋められました。Google Apps ScriptのロギングをGoogle CloudのStackdriver ロギング（現在はOperations Suiteと呼ばれています）と統合し、アプリケーションのロギング、監視、およびデバッグのための中央集権的なプラットフォームを提供しました。これにより、スケールでのロギングだけでなく、ログベースのメトリクス、リアルタイムのログ解析、他のGoogle Cloudサービスとの統合など、高度なログ管理機能が利用可能になりました。

`Logger`は依然として小規模なスクリプトでの迅速なデバッグとロギングの目的には役立ちますが、`console.log()`を使用する進化は、スケーラブルでクラウドネイティブなアプリケーションを開発するための広範なシフトを反映しています。これは、今日のアプリケーションの複雑さとスケールに対応するツールを開発者に提供するGoogleのコミットメントを強調しています。しかし、新参者はGoogle Cloud Platformのコンセプトに慣れる必要があるやや急な学習曲線に注意する必要があります。それにもかかわらず、クラウド機能を十分に活用することを目指す開発者にとって有利です。クラウドサービスとのこの整合性は、クラウドコンピューティングの時代における堅牢でスケーラブルなロギングメカニズムの重要性を強調するソフトウェア開発の広範なトレンドの一部です。
