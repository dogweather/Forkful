---
date: 2024-01-26 01:08:08.818320-07:00
description: "\u30ED\u30B0\u3068\u306F\u3001\u57FA\u672C\u7684\u306B\u30B3\u30FC\u30C9\
  \u3092\u901A\u3058\u3066\u30D1\u30F3\u304F\u305A\u30EA\u30B9\u30C8\u3092\u6B8B\u3059\
  \u3053\u3068\u3067\u3059\u3002\u3053\u308C\u306B\u3088\u3063\u3066\u3001\u30B9\u30AF\
  \u30EA\u30D7\u30C8\u304C\u5B9F\u969B\u306B\u5B9F\u884C\u3055\u308C\u3066\u3044\u308B\
  \u3068\u304D\u306B\u4F55\u304C\u8D77\u3053\u3063\u3066\u3044\u308B\u306E\u304B\u3092\
  \u8FFD\u8DE1\u3059\u308B\u3053\u3068\u304C\u3067\u304D\u307E\u3059\u3002\u30D7\u30ED\
  \u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30C7\u30D0\u30C3\u30B0\u3059\u308B\u305F\u3081\
  \u3001\u30A2\u30D7\u30EA\u306E\u52D5\u4F5C\u3092\u8FFD\u8DE1\u3059\u308B\u305F\u3081\
  \u3001\u30D1\u30D5\u30A9\u30FC\u30DE\u30F3\u30B9\u3092\u76E3\u8996\u3059\u308B\u305F\
  \u3081\u3001\u305D\u3057\u3066\u4E0D\u6B63\u884C\u70BA\u3092\u898B\u5F35\u308B\u305F\
  \u3081\u306B\u30ED\u30B0\u3092\u4F7F\u7528\u3057\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:42.447151-06:00'
model: gpt-4-1106-preview
summary: "\u30ED\u30B0\u3068\u306F\u3001\u57FA\u672C\u7684\u306B\u30B3\u30FC\u30C9\
  \u3092\u901A\u3058\u3066\u30D1\u30F3\u304F\u305A\u30EA\u30B9\u30C8\u3092\u6B8B\u3059\
  \u3053\u3068\u3067\u3059\u3002\u3053\u308C\u306B\u3088\u3063\u3066\u3001\u30B9\u30AF\
  \u30EA\u30D7\u30C8\u304C\u5B9F\u969B\u306B\u5B9F\u884C\u3055\u308C\u3066\u3044\u308B\
  \u3068\u304D\u306B\u4F55\u304C\u8D77\u3053\u3063\u3066\u3044\u308B\u306E\u304B\u3092\
  \u8FFD\u8DE1\u3059\u308B\u3053\u3068\u304C\u3067\u304D\u307E\u3059\u3002\u30D7\u30ED\
  \u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30C7\u30D0\u30C3\u30B0\u3059\u308B\u305F\u3081\
  \u3001\u30A2\u30D7\u30EA\u306E\u52D5\u4F5C\u3092\u8FFD\u8DE1\u3059\u308B\u305F\u3081\
  \u3001\u30D1\u30D5\u30A9\u30FC\u30DE\u30F3\u30B9\u3092\u76E3\u8996\u3059\u308B\u305F\
  \u3081\u3001\u305D\u3057\u3066\u4E0D\u6B63\u884C\u70BA\u3092\u898B\u5F35\u308B\u305F\
  \u3081\u306B\u30ED\u30B0\u3092\u4F7F\u7528\u3057\u307E\u3059\u3002."
title: "\u30ED\u30AE\u30F3\u30B0"
weight: 17
---

## 使い方:
以下は、スクリプトに基本的なログを挿入する方法についてです：

```PowerShell
# 簡単なログメッセージの作成
Write-Host "情報: スクリプトの処理を開始します。"

# ファイルへの書き込み
"情報: これはログに記録されたメッセージです。" | Out-File -Append myLog.log

# より詳細なログのための組み込みcmdletの使用
Start-Transcript -Path "./detailedLog.log"
Write-Output "警告: 何かが少し正しくありません。"
# ... あなたのスクリプトは何かする
Stop-Transcript

# detailedLog.logの出力
******************************
Windows PowerShell トランスクリプト開始
開始時刻: 20230324112347
ユーザー名  : PShellGuru@example.com
RunAsユーザー: PShellGuru@example.com
コンフィギュレーション名: 
マシン  : PS-DEVBOX (Microsoft Windows NT 10.0.17763.0)
ホストアプリケーション: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
プロセスID: 2024
PS バージョン: 7.1.2
```

これで、ログにはコードが何をしていたのかの一連の動作が記録されます。

## 深掘り:
歴史的に見て、ログはプログラミング自体が始まった頃から存在しています。ソフトウェアのための船長のログのようなものです。昔は出力やテレタイプ機が使われていましたが、現在ではファイルや洗練されたログ管理システムが全てです。

PowerShellの深いところで作業をしているとき、`Write-Host`は素早くて簡単ですが、テキストをコンソールに出力するだけで、記録を保持するには適していません。`Out-File`はテキストをファイルに簡単に投げる方法を提供しますが、本当に重要な情報を得るためには、入力、出力、その他全てをログに記録する`Start-Transcript`と`Stop-Transcript`を使用することをお勧めします。

代替手段？もしエンタープライズ環境で作業しているなら、Windowsイベントログを見たり、Logstashのようなソフトウェアを使用することを検討するかもしれませんが、日常のスクリプトではPowerShellのツールを使い続けるのが良いでしょう。実装にあたっては、賢くログを取ることを忘れないでください—少なすぎても無駄になるし、多すぎてもホワイトノイズになります。

## 参照:
以下をチェックして、PowerShellでのログ取りの全体像を掴みましょう：
