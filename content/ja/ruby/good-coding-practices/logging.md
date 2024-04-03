---
date: 2024-01-26 01:08:59.579545-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:42.863913-06:00'
model: gpt-4-1106-preview
summary: "\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u306B\u304A\u3051\u308B\u30ED\
  \u30B0\u3068\u306F\u3001\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u306E\u65E5\
  \u8A18\u306E\u3088\u3046\u306A\u3082\u306E\u3067\u3059\u3002\u305D\u308C\u306F\u3001\
  \u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u304C\u4F55\u3092\u3057\u3066\u3044\
  \u308B\u306E\u304B\u3001\u3069\u306E\u3088\u3046\u306B\u632F\u308B\u821E\u3063\u3066\
  \u3044\u308B\u306E\u304B\u3092\u7406\u89E3\u3059\u308B\u305F\u3081\u306E\u3001\u30A4\
  \u30D9\u30F3\u30C8\u3084\u30E1\u30C3\u30BB\u30FC\u30B8\u3001\u30C7\u30FC\u30BF\u30DD\
  \u30A4\u30F3\u30C8\u306E\u4F53\u7CFB\u7684\u306A\u8A18\u9332\u3067\u3059\u3002\u30D7\
  \u30ED\u30B0\u30E9\u30DE\u30FC\u304C\u30ED\u30B0\u3092\u53D6\u308B\u306E\u306F\u3001\
  \u30C7\u30D0\u30C3\u30B0\u3001\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u306E\
  \u5065\u5168\u6027\u306E\u76E3\u8996\u3001\u5927\u554F\u984C\u306B\u767A\u5C55\u3059\
  \u308B\u524D\u306B\u6F5C\u5728\u7684\u306A\u554F\u984C\u306B\u3064\u3044\u3066\u306E\
  \u624B\u304C\u304B\u308A\u3092\u5F97\u308B\u305F\u3081\u306B\u91CD\u8981\u3060\u304B\
  \u3089\u3067\u3059\u3002."
title: "\u30ED\u30AE\u30F3\u30B0"
weight: 17
---

## 使い方：
Rubyには`Logger`という名前の組み込みモジュールがあり、非常に簡単に使うことができます。始めるための簡単な例を以下に示します：

```ruby
require 'logger'

# 標準出力に出力するLoggerを作成
logger = Logger.new(STDOUT)
logger.level = Logger::INFO

# ログメッセージの例
logger.info("This is an info message")
logger.warn("This is a warning message")
logger.error("This is an error message")
```

上記のスクリプトを実行すると、次のような出力が得られます：

```
I, [2023-03-15T10:00:00.123456 #1234]  INFO -- : This is an info message
W, [2023-03-15T10:00:01.234567 #1234]  WARN -- : This is a warning message
E, [2023-03-15T10:00:02.345678 #1234] ERROR -- : This is an error message
```

ログのフォーマットやレベルを設定して余計なノイズを除外したり、ログをファイルや外部ロギングサービスなど異なる出力に向けることができます。

## 詳細な潜入
ログはプログラミングにおいて古くからの伝統のようなものです。歴史的に、ログは`grep`のようなツールで手動で解析されるシンプルなテキストファイルでした。しかし、この概念は、Log4j、LinuxのSyslog、クラウド時代のSematextやLogglyのような堅牢なログフレームワークやサービスの全体的なエコシステムへと発展しました。

Rubyの`Logger`は、始めるための飾り気のない方法ですが、もしより多くの馬力と柔軟性が必要なら、LogrageやSemantic Loggerのような代替品をチェックすると良いでしょう。これらのライブラリはRubyアプリケーションとよく連携し、ログフォーマットのより細かい制御（JSONフォーマットの構造化ログを含む）、より良いパフォーマンス、他のサービスとのシームレスな統合を提供します。

各Rubyログライブラリはそれぞれ独自の方法を持っていますが、裏側では、メッセージを送るロガーインスタンスというアイデアを中心に展開しています。ロガーは設定されたレベル—DEBUG, INFO, WARN, ERROR, FATAL, UNKNOWN—に基づいてこれらのメッセージを処理し、それらをどうするかを決定します：印刷する、ファイルに保存する、ネットワークを通じて送信するなど。

## 参照
Rubyの組み込みログモジュールについて詳しく知りたい場合は、公式ドキュメントをチェックしてください：

もしより高度なロギングに興味があるか、サードパーティのgemを探求したい場合は：
- [Lograge](https://github.com/roidrage/lograge)

一般的なログ取りの実践や哲学について（Ruby特有ではない）、これらの記事は時間を超えた読み物です：
- [Googleのサイト信頼性エンジニアリングブック - 第16章：過負荷の処理](https://sre.google/sre-book/handling-overload/#log-messages)
- [The 12 Factor App - Logs](https://12factor.net/logs)
