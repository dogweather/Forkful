---
title:                "コマンドライン引数の読み込み"
aliases:
- ja/vba/reading-command-line-arguments.md
date:                  2024-02-01T21:59:47.034464-07:00
model:                 gpt-4-0125-preview
simple_title:         "コマンドライン引数の読み込み"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/vba/reading-command-line-arguments.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 何となぜ？

Visual Basic for Applications（VBA）でコマンドライン引数を読み取るというのは、実行時にプログラムに渡されたパラメータにアクセスすることを意味します。この技術は、ユーザーの介入なしにプログラムの動作や出力を影響を与えるためによく使用され、自動化やスクリプティングのタスクを大幅にシンプルかつ多用途にします。

## 使い方：

他の単純なプログラミング環境とは異なり、VBAは主にMicrosoft Officeアプリケーション内での埋め込み用に設計されているため、一般的な意味で直接コマンドライン引数を読み取るための組み込み機能はありません。しかし、ちょっとした創造性を使えば、Windows Script Host（WSH）を使用するか、外部APIを呼び出すことで類似の機能を実現できます。以下はWSHを使用した実用的な回避策です：

1. **VBAへ引数を渡すVBScriptを作成する：**

   最初に、VBAアプリケーション（例：Excelマクロ）を起動し、コマンドライン引数を渡すVBScriptファイル（*yourScript.vbs*）を作成します：

```vb
Set objExcel = CreateObject("Excel.Application")
objExcel.Workbooks.Open "C:\YourMacroWorkbook.xlsm"
objExcel.Run "YourMacroName", WScript.Arguments.Item(0), WScript.Arguments.Item(1)
objExcel.Quit
```

2. **VBAで引数にアクセスする：**

   VBAアプリケーション（*YourMacroWorkbook.xlsm*）で、パラメータを受け入れるようにマクロ（*YourMacroName*）を修正または作成します：

```vb
Sub YourMacroName(arg1 As String, arg2 As String)
    MsgBox "Argument 1: " & arg1 & " Argument 2: " & arg2
End Sub
```

3. **スクリプトを実行する：**

   コマンドラインから引数を指定してVBScriptを実行します：

```shell
cscript yourScript.vbs "Hello" "World"
```

   これにより、"Hello" と "World" の引数でVBAマクロが実行され、メッセージボックスにそれらが表示されるはずです。

## 詳細分析：

歴史的な文脈で、VBAはMicrosoft Officeアプリケーションの機能を拡張するために考案されましたが、独立したプログラミング環境としてではありません。そのため、コマンドラインとの直接のやりとりはその主要な範囲外であり、コマンドライン引数を読み取るための組み込みサポートがないことを説明しています。

上述の方法は効果的ですが、外部スクリプティングを利用してギャップを埋めるネイティブソリューションよりも回避策にすぎません。このアプローチは、マクロを有効にする必要があり、実行するためにセキュリティ設定を下げる可能性があるため、複雑さと潜在的なセキュリティ上の懸念を生じさせます。

コマンドライン引数に大きく依存しているタスクや、Windowsオペレーティングシステムとのよりシームレスな統合が必要な場合、PowerShellやPythonのような他のプログラミング言語が、より堅牢で安全なソリューションを提供するかもしれません。これらの代替案はコマンドライン引数を直接サポートしており、外部入力によって動的にその動作を変更する必要があるスタンドアロンアプリケーションやスクリプトに適しています。
