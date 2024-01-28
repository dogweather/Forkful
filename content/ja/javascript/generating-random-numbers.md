---
title:                "乱数の生成"
date:                  2024-01-27T20:34:34.021255-07:00
model:                 gpt-4-0125-preview
simple_title:         "乱数の生成"
programming_language: "Javascript"
category:             "Javascript"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/javascript/generating-random-numbers.md"
---

{{< edit_this_page >}}

## 何となぜ？

JavaScriptで乱数を生成する技術は、ランダムな敵の行動が必要なゲームから、暗号的なランダムさを必要とするセキュリティアルゴリズムまで、アプリケーションの予測不可能性を作り出すために使用されます。この能力は、ダイナミックなユーザーエクスペリエンスと安全なアプリケーションの開発にとって重要です。

## 方法：

### 基本的な乱数生成

JavaScriptで乱数を生成するもっとも簡単な方法は、`Math.random()`を使用することです。この関数は、0（含む）から1（含まない）までの範囲の浮動小数点で擬似乱数を返します。

```javascript
let randomNumber = Math.random();
console.log(randomNumber);
```

### 範囲内での乱数生成

しばしば、特定の範囲内のランダムな整数が欲しい場合があります。これは、`Math.random()`の出力をスケーリングして丸めることにより実現できます。

```javascript
function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

console.log(getRandomInt(1, 100));
```

### 暗号学的に安全な乱数

ランダムさの度合いがより高い（例えば、暗号化操作など）アプリケーションには、`crypto.getRandomValues()`メソッドを使用できます。これは、`Math.random()`によって生成される擬似乱数とは異なり、暗号化ランダムさを提供します。

```javascript
(function generateSecureRandom() {
  let array = new Uint32Array(1);
  window.crypto.getRandomValues(array);
  console.log(array[0]);
})();
```

## 詳細

歴史的に、JavaScriptでの乱数生成は`Math.random()`関数にのみ依存していました。大半の一般的な使用例には便利ですが、そのアルゴリズムは、メルセンヌ・ツイスターなどの擬似乱数生成器（PRNG）の変種が一般的で、暗号化セキュリティを提供しません。

Web Cryptography APIの導入により、`crypto.getRandomValues()`メソッドが提供され、セキュリティに敏感なアプリケーションに向けて予測がはるかに難しく適した数値を生成する方法が提供されました。この方法は、暗号化操作に適したより頑強な`/dev/random`など、基礎となるオペレーティングシステムのランダムソースにアクセスします。

任務に適した方法を選択することが重要です。`Math.random()`は簡単なゲーム、アニメーション、あるいはランダムの品質が重視されない場合に十分です。しかし、パスワードリセットトークンや暗号化操作などのセキュリティ機能については、その優れたランダム品質のために`crypto.getRandomValues()`がより良い選択肢となります。

特に`Math.random()`は、ほとんどの実装で既知の偏りを持つ数値を生成します。つまり、一部の数値が他よりも発生しやすいということです。この偏りはごく小さく、通常のアプリケーションではほとんど感じられないものの、暗号文脈やオンラインギャンブルのような公正さが重要なアプリケーションでは`Math.random()`の使用を不適格とします。

結論として、JavaScriptの内蔵された乱数生成機能は幅広いニーズをカバーしますが、それぞれの方法の違いと制限を理解することは、適切な適用に不可欠です。
