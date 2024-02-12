---
title:                "リファクタリング"
aliases:
- ja/google-apps-script/refactoring.md
date:                  2024-02-01T22:00:08.576651-07:00
model:                 gpt-4-0125-preview
simple_title:         "リファクタリング"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/google-apps-script/refactoring.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 何となぜ？

プログラミングの用語でリファクタリングは、既存のコード構造を変更すること—外部動作を変えずにファクタリングを変更すること—を指し、非機能属性を改善することです。これは、コードの読みやすさを高め、複雑さを減らし、潜在的なバグを発見し易くするなど、メンテナンスの容易さや将来的なコードのスケーラビリティを促進するために、プログラマーにとって重要なステップです。

## 方法:

Google Apps Scriptにおいて、リファクタリングの恩恵を受ける一般的なシナリオは、Google SheetsやDocsとやり取りする手間のかかるスクリプトの簡素化です。初期には、結果を早く得るために、スクリプトが手っ取り早く書かれることがあります。時間が経つにつれ、スクリプトが成長すると、扱いにくくなります。より読みやすく、効率的なリファクタリングの例を紹介しましょう。

**オリジナルスクリプト:**

```javascript
function logSheetNames() {
  var sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  for (var i = 0; i < sheets.length; i++) {
    Logger.log(sheets[i].getName());
  }
}
```

この関数は、Google スプレッドシートの各シートの名前をログに記録します。問題なく動作しますが、古いJavaScriptの慣習を使用しており、明確さに欠けます。

**リファクタリングされたスクリプト:**

```javascript
function logSheetNames() {
  const sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  sheets.forEach(sheet => Logger.log(sheet.getName()));
}
```

リファクタリングされたバージョンでは、変更しない変数には`const`を使用することで、意図を明確にしました。また、配列を反復処理するより現代的で簡潔なアプローチである`forEach`メソッドも使用しており、可読性が向上しています。

**サンプル出力（両スクリプト共通）:**

Loggerの出力は以下のようになります。Google Sheetsドキュメントに「Expenses」と「Revenue」という名前の2つのシートがあると仮定します：

```
[20-04-2023 10:00:00: INFO] Expenses
[20-04-2023 10:00:01: INFO] Revenue
```

リファクタリングされたスクリプトは、同じ結果を達成しつつ、よりクリーンで一目で理解しやすくなっています。

## 深掘り

Google Apps Scriptでのリファクタリングは、その原則の一部を、より広いソフトウェアエンジニアリングの実践から継承しています。特に、1999年のマーティン・ファウラーの画期的な書籍「Refactoring: Improving the Design of Existing Code」によって、リファクタリングはさまざまな技法に関する包括的なガイドを提供し、概念としてより認識され、構造化されました。リファクタリングの具体的な内容はプログラミング言語の文法的および機能的な違いにより異なる場合がありますが、コアの目標は同じです：外部の動作を変更せずにコードを改善することです。

Google Apps Scriptの文脈では、リファクタリング中に考慮すべき主要な側面は、Googleによって課されるサービスのクオータと制限です。効率的にリファクタリングされたコードは、読みやすくだけでなく、これらの制約の中でより速く、より信頼性高く実行されます。たとえば、バッチ操作（一度に一つのセルに値を設定する代わりに`Range.setValues()`を使用するなど）は、実行時間とクオータの消費を大幅に削減することができます。

ただし、特定の複雑なプロジェクトの場合、これらの制限のためにGoogle Apps Scriptが不足することがあります。そのような場合、Google Cloud FunctionsやApps Scriptの新しい兄弟であるAppSheetを検討すると、より良いスケーラビリティと機能性を提供するかもしれません。

結局のところ、Google Apps Scriptプロジェクトを維持し、改善する上でリファクタリングは重要なスキルですが、環境の制限を理解し、代替解決策を検討することも、効率的で堅牢で、メンテナンス可能なコードを提供する上で同じくらい重要です。
