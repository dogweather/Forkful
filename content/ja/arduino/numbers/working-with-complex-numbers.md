---
date: 2024-01-26 04:36:57.590884-07:00
description: "\u8907\u7D20\u6570\u306B\u306F\u5B9F\u90E8\u3068\u865A\u90E8\u304C\u3042\
  \u308A\u3001\u901A\u5E38`a + bi`\u3068\u3057\u3066\u8A18\u8FF0\u3055\u308C\u307E\
  \u3059\u3002\u4FE1\u53F7\u51E6\u7406\u3084\u96FB\u6C17\u5DE5\u5B66\u3001\u307E\u305F\
  \u306F\u73FE\u8C61\u304C\u5E73\u9762\u4E0A\u3067\u6700\u3082\u3088\u304F\u30E2\u30C7\
  \u30EB\u5316\u3055\u308C\u308B\u305D\u306E\u4ED6\u306E\u5206\u91CE\u3092\u542B\u3080\
  \u3001\u6570\u5B66\u3092\u591A\u7528\u3059\u308BArduino\u30D7\u30ED\u30B8\u30A7\u30AF\
  \u30C8\u306B\u4E0D\u53EF\u6B20\u3067\u3059\u3002"
lastmod: '2024-03-13T22:44:42.488384-06:00'
model: gpt-4-0125-preview
summary: "\u8907\u7D20\u6570\u306B\u306F\u5B9F\u90E8\u3068\u865A\u90E8\u304C\u3042\
  \u308A\u3001\u901A\u5E38`a + bi`\u3068\u3057\u3066\u8A18\u8FF0\u3055\u308C\u307E\
  \u3059\u3002\u4FE1\u53F7\u51E6\u7406\u3084\u96FB\u6C17\u5DE5\u5B66\u3001\u307E\u305F\
  \u306F\u73FE\u8C61\u304C\u5E73\u9762\u4E0A\u3067\u6700\u3082\u3088\u304F\u30E2\u30C7\
  \u30EB\u5316\u3055\u308C\u308B\u305D\u306E\u4ED6\u306E\u5206\u91CE\u3092\u542B\u3080\
  \u3001\u6570\u5B66\u3092\u591A\u7528\u3059\u308BArduino\u30D7\u30ED\u30B8\u30A7\u30AF\
  \u30C8\u306B\u4E0D\u53EF\u6B20\u3067\u3059\u3002."
title: "\u8907\u7D20\u6570\u306E\u6271\u3044\u65B9"
weight: 14
---

## 使い方：
```Arduino
#include <Complex.h>

void setup() {
  Serial.begin(9600); // シリアル通信を開始
  
  Complex myComplex(2, 3); // 複素数 2 + 3i を作成
  Complex anotherComplex(1, 1); // 別の複素数 1 + 1i を作成
  
  // 加算
  Complex result = myComplex + anotherComplex; 
  Serial.print("加算: "); 
  result.print(); // 出力は 3 + 4i
  
  // 乗算
  result = myComplex * anotherComplex; 
  Serial.print("乗算: ");
  result.print(); // 出力は -1 + 5i
}

void loop() {
  // この例では使用されません
}
```
サンプル出力：
```
加算: 3 + 4i
乗算: -1 + 5i
```

## 深く掘り下げる
元々、複素数は懐疑的に受け入れられましたが、さまざまな科学分野の中心となっています。歴史的には、実際の解を欠く多項式方程式の解を提供することで認められました。

Arduinoは標準ライブラリに複素数を含んでいませんが、`Complex.h`のようなライブラリを活用して扱うことができます。これらのライブラリ内部では、通常、実部と虚部を2つのダブルで格納し、算術をサポートするために演算子をオーバーロードするComplexクラスを定義します。

代替案として、本質的に複素数の算術を必要としないアプリケーションでは、他の数学戦略やライブラリの使用を検討してください。ただし、複素数の代わりに浮動小数点を使用すると、一部の問題が過度に単純化される可能性があることを覚えておいてください。

## 参照
- Rob Tillaartによる[Complex.h](https://github.com/RobTillaart/Complex)ライブラリ。
- 複素数の背後にある[数学に関する深い探究](https://mathworld.wolfram.com/ComplexNumber.html)。
