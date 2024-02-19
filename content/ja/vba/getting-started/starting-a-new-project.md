---
aliases:
- /ja/vba/starting-a-new-project/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:03:02.997580-07:00
description: "Visual Basic for Applications\uFF08VBA\uFF09\u3067\u65B0\u3057\u3044\
  \u30D7\u30ED\u30B8\u30A7\u30AF\u30C8\u3092\u59CB\u3081\u308B\u306B\u306F\u3001Excel\u306A\
  \u3069\u306E\u30DB\u30B9\u30C8\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u5185\
  \u3067\u74B0\u5883\u3092\u8A2D\u5B9A\u3057\u3001\u30BF\u30B9\u30AF\u3092\u81EA\u52D5\
  \u5316\u3059\u308B\u304B\u6A5F\u80FD\u3092\u62E1\u5F35\u3059\u308B\u3053\u3068\u304C\
  \u542B\u307E\u308C\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\
  Microsoft\u2026"
lastmod: 2024-02-18 23:08:54.761332
model: gpt-4-0125-preview
summary: "Visual Basic for Applications\uFF08VBA\uFF09\u3067\u65B0\u3057\u3044\u30D7\
  \u30ED\u30B8\u30A7\u30AF\u30C8\u3092\u59CB\u3081\u308B\u306B\u306F\u3001Excel\u306A\
  \u3069\u306E\u30DB\u30B9\u30C8\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u5185\
  \u3067\u74B0\u5883\u3092\u8A2D\u5B9A\u3057\u3001\u30BF\u30B9\u30AF\u3092\u81EA\u52D5\
  \u5316\u3059\u308B\u304B\u6A5F\u80FD\u3092\u62E1\u5F35\u3059\u308B\u3053\u3068\u304C\
  \u542B\u307E\u308C\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\
  Microsoft\u2026"
title: "\u65B0\u30D7\u30ED\u30B8\u30A7\u30AF\u30C8\u306E\u958B\u59CB"
---

{{< edit_this_page >}}

## 何となく何故か？

Visual Basic for Applications（VBA）で新しいプロジェクトを始めるには、Excelなどのホストアプリケーション内で環境を設定し、タスクを自動化するか機能を拡張することが含まれます。プログラマーは、Microsoft Officeアプリケーションのカスタマイズと自動化でVBAの力を活用し、ワークフローを合理化し、生産性を向上させるために、この領域に踏み込みます。

## 方法：

新しいVBAプロジェクトを始める準備ができたら、通常、VBAエディタにアクセスしてプロジェクトフレームワークを初期化することから始まります。ホストアプリケーションとしてExcelを使用して手順を詳しく見ていきましょう：

1. **VBAエディタを開く**：Excelで`Alt + F11`を押してVBAエディタにアクセスします。
2. **新しいモジュールを挿入**：メニューから`挿入 > モジュール`に移動し、プロジェクトに新しいモジュールを追加します。これがコードが置かれる場所です。
3. **最初のマクロを書く**：メッセージボックスを表示するシンプルなマクロをコーディングしましょう。以下のコードをモジュールに入力します：

```vb
Sub SayHello()
    MsgBox "Hello, World!", vbInformation, "Greetings"
End Sub
```

4. **マクロを実行する**：`SayHello`サブ内にカーソルがある状態で`F5`を押すか、`実行 > Run Sub/UserForm`に移動して`SayHello`を選択します。"Hello, World!"と表示されたメッセージボックスがポップアップするはずです。

サンプル出力：

```plaintext
"Hello, World!"が表示されたメッセージボックス。
```

5. **プロジェクトを保存する**：終了する前に、作業を保存してください。Excelワークブックが以前に保存されていなかった場合、マクロ有効ワークブック（`.xlsm`ファイル形式）として保存するように求められます。

## 詳細な調査

Visual Basic for Applicationsは、1993年の導入以来、Microsoftの自動化戦略の要となってきました。その前身であるMacroBasicの進化として始まったVBAは、MicrosoftのOfficeスイート全体にわたる改善された統合を備えた、より堅牢なソリューションを提供しました。VBAへの移行は重要であり、完全なプログラミング言語の力を活用したより複雑なスクリプト作成能力に向けたシフトを示していました。

その年齢にもかかわらず、VBAは今日のオフィス環境で広く使われており、それはOffice製品内の深い統合と多くの組織でのレガシーコードの広範な基盤によるものです。しかし、新しいWebベースのアプリケーションや、Office以外のアプリケーションとのより多くのスケーラビリティと統合が必要なタスクの場合、Pythonのような豊富なライブラリエコシステムを備えた言語や、オフィススクリプトのためのJavaScriptなどの代替手段が、より現代的かつ汎用的なアプローチを提供します。これらの代替手段は、より急な学習曲線とセットアップを要求しますが、バージョン管理やデプロイメントパイプラインなどの現代の開発慣行をサポートする、より広い適用性を提供します。
