---
aliases:
- /ja/javascript/refactoring/
date: 2024-01-26 01:42:14.772529-07:00
description: "\u30EA\u30D5\u30A1\u30AF\u30BF\u30EA\u30F3\u30B0\u306F\u3001\u65E2\u5B58\
  \u306E\u30B3\u30F3\u30D4\u30E5\u30FC\u30BF\u30B3\u30FC\u30C9\u306E\u69CB\u9020\u3092\
  \u5916\u90E8\u306E\u6319\u52D5\u3092\u5909\u3048\u305A\u306B\u518D\u69CB\u7BC9\u3059\
  \u308B\u30D7\u30ED\u30BB\u30B9\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\
  \u306F\u3001\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\u306E\u975E\u6A5F\u80FD\u7684\u5C5E\
  \u6027\u3092\u6539\u5584\u3059\u308B\u305F\u3081\u306B\u3053\u308C\u3092\u884C\u3044\
  \u3001\u30B3\u30FC\u30C9\u3092\u3088\u308A\u30AF\u30EA\u30A2\u3067\u52B9\u7387\u7684\
  \u306B\u3057\u3001\u305D\u308C\u306B\u3088\u3063\u3066\u30E1\u30F3\u30C6\u30CA\u30F3\
  \u30B9\u3092\u7C21\u7D20\u5316\u3057\u3001\u5C06\u6765\u306E\u6A5F\u80FD\u8FFD\u52A0\
  \u3092\u5BB9\u6613\u306B\u3057\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:55.276900
model: gpt-4-0125-preview
summary: "\u30EA\u30D5\u30A1\u30AF\u30BF\u30EA\u30F3\u30B0\u306F\u3001\u65E2\u5B58\
  \u306E\u30B3\u30F3\u30D4\u30E5\u30FC\u30BF\u30B3\u30FC\u30C9\u306E\u69CB\u9020\u3092\
  \u5916\u90E8\u306E\u6319\u52D5\u3092\u5909\u3048\u305A\u306B\u518D\u69CB\u7BC9\u3059\
  \u308B\u30D7\u30ED\u30BB\u30B9\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\
  \u306F\u3001\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\u306E\u975E\u6A5F\u80FD\u7684\u5C5E\
  \u6027\u3092\u6539\u5584\u3059\u308B\u305F\u3081\u306B\u3053\u308C\u3092\u884C\u3044\
  \u3001\u30B3\u30FC\u30C9\u3092\u3088\u308A\u30AF\u30EA\u30A2\u3067\u52B9\u7387\u7684\
  \u306B\u3057\u3001\u305D\u308C\u306B\u3088\u3063\u3066\u30E1\u30F3\u30C6\u30CA\u30F3\
  \u30B9\u3092\u7C21\u7D20\u5316\u3057\u3001\u5C06\u6765\u306E\u6A5F\u80FD\u8FFD\u52A0\
  \u3092\u5BB9\u6613\u306B\u3057\u307E\u3059\u3002"
title: "\u30EA\u30D5\u30A1\u30AF\u30BF\u30EA\u30F3\u30B0"
---

{{< edit_this_page >}}

## 何となぜ？
リファクタリングは、既存のコンピュータコードの構造を外部の挙動を変えずに再構築するプロセスです。プログラマーは、ソフトウェアの非機能的属性を改善するためにこれを行い、コードをよりクリアで効率的にし、それによってメンテナンスを簡素化し、将来の機能追加を容易にします。

## 方法：

リファクタリングがどのようにコードをより簡潔で読みやすくするかの簡単な例を見てみましょう。ここでは、数字の配列の合計を計算する関数をリファクタリングします。

変更前：
```javascript
function calculateSum(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
}

console.log(calculateSum([1, 2, 3, 4])); // 出力: 10
```

変更後：
```javascript
function calculateSum(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}

console.log(calculateSum([1, 2, 3, 4])); // 出力: 10
```

`reduce` メソッドが機能をそのままに関数のサイズを削減する方法がわかりますか？それがリファクタリングです。

## 深掘り

リファクタリングが正式な実践として浮上したのは、1999年のマーチン・ファウラーの著書『Refactoring: Improving the Design of Existing Code』の出版までありませんでした。この本は、アジャイルソフトウェア開発の台頭とともに、リファクタリングを主流に押し上げるのを助けました。

リファクタリングをソフトウェア開発の観点から説明することは、なぜ作業場を片付けるかを説明することに似ています：次に何か（この場合はコード）を修正する必要がある時に、混乱を扱うのに時間をかけることなく、実際の問題にもっと集中できるようにするためです。

リファクタリングへの代替策について語るとき、私たちはソフトウェア保守戦略についてのより広い議論に足を踏み入れます。例えば、完全な書き換えを選択することもできますが、それはしばしばより高コストでリスキーです。インクリメンタルにリファクタリングすると、突然の大規模変更から船を沈めることなく、継続的な利益を享受できます。

リファクタリングは、統合開発環境（IDE）やJSHint、ESLint、PrettierなどのJavaScriptエコシステムのツールの開発によって助けられてきました。これらはコード品質チェックを自動化し、リファクタリングの機会を強調表示します。

すべては、クリーンで表現力豊かで保守可能なコードについてです。リファクタリングプロセスの一部として、洗練されたアルゴリズム、データ構造の最適化、あるいは手続き型から関数型プログラミングスタイルへの切り替えなどのアーキテクチャの変更も含まれるかもしれません。

リファクタリングは慎重に行う必要があります。変更がソフトウェアの挙動を予期せずに変更していないことを確認するために頑健なテストセットが不可欠です。これが、リファクタリングと良く合うテスト駆動開発（TDD）のもう一つの理由です。それはデフォルトでその安全ネットを提供します。

## 関連項目

- マーチン・ファウラーのリファクタリングの本：[Refactoring - Improving the Design of Existing Code](https://martinfowler.com/books/refactoring.html)
- JavaScriptテストフレームワーク（リファクタリングが機能を壊さないようにするために）：
  - Jest：[Jest - Delightful JavaScript Testing](https://jestjs.io/)
  - Mocha：[Mocha - 楽しく、シンプルで、柔軟なJavaScriptテストフレームワーク](https://mochajs.org/)

- コード品質とリファクタリングサポートのためのツール：
  - ESLint：[ESLint - プラグイン可能なJavaScriptリンター](https://eslint.org/)
  - Prettier：[Prettier - 意見のあるコードフォーマッター](https://prettier.io/)
