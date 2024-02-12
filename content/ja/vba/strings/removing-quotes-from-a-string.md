---
title:                "文字列から引用符を削除する"
aliases:
- /ja/vba/removing-quotes-from-a-string/
date:                  2024-02-01T22:00:31.763565-07:00
model:                 gpt-4-0125-preview
simple_title:         "文字列から引用符を削除する"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/vba/removing-quotes-from-a-string.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 何となぜ？

VBAで文字列から引用符を削除することは、文字列に含まれるかもしれない単一（`'`）または二重（`"`）引用符の出現を取り除く操作を意味します。この操作は、データの清潔化のために不可欠であり、データベースクエリ、JSONの解析、またはアプリケーションのインターフェイス内での美的または一貫性のある理由から正しく文字列をフォーマットすることを保証します。

## 方法：

VBAでは、文字列から引用符を削除するための複数のアプローチがあります。ここでは`Replace`関数を使用した直接的な例を紹介します。この関数は、特定の文字列（この場合は引用符）を別の文字列（削除する場合は空の文字列）に置き換えるために、文字列内を検索します。

```basic
Sub RemoveQuotesExample()
    Dim originalString As String
    originalString = "'This' is a ""test"" string."
    
    ' 単一引用符を削除
    originalString = Replace(originalString, "'", "")
    
    ' 二重引用符を削除
    originalString = Replace(originalString, Chr(34), "")
    
    Debug.Print originalString '出力: This is a test string.
End Sub
```

二重引用符の場合は`Chr(34)`を使用することに注意してください。これは、二重引用符がASCII文字34だからです。VBAでは二重引用符も文字列リテラルを示すために使用されるため、これが必要です。

引用語内部など、引用符が必要な形式の一部であるより微妙なシナリオでは、Regexを使用するか、一文字ずつ解析するなど、より高度なロジックが必要になるかもしれません。

## 深い潜水

VBAは、Microsoft Officeスイート内でのタスクの自動化において主要なツールであり、`Replace`のような文字列操作関数の豊富なセットを提供します。しかし、この関数は、VBAが文字列操作において実現できることの表面をかすめるだけです。

歴史的に、VBAはその前身からオフィス自動化タスクのための単純さを重視してきました。そのため、`Replace`のような関数の実装が直接的です。しかし、複雑な文字列操作や清潔化を伴う現代のプログラミングタスクでは、VBAはその限界を示すかもしれません。

そのような場合、プログラマーは文字列の解析や操作においてより柔軟性と力を持つため、正規表現（`VBScript_RegExp_55.RegExp`オブジェクト経由）とVBAを組み合わせることがあります。しかし、このアプローチは追加の複雑さを導入し、すべてのユーザーに適しているとは限らない正規表現パターンの確かな理解を必要とします。

その限界にもかかわらず、VBAの`Replace`関数は、文字列から引用符を削除する多くの一般的なシナリオを効率的にカバーします。これは、より複雑な正規表現領域に深く潜ることなく、ほとんどの文字列操作ニーズに対する迅速かつ簡単な解決策として機能します。`Replace`や他の基本的な文字列関数ができることの限界に達した人々は、VBA内で正規表現を探求するか、複雑な文字列操作に適したより堅牢な言語に移ることを次の最良のステップとして考えるかもしれません。
