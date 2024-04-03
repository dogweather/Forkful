---
date: 2024-01-26 01:09:24.414714-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:42.504622-06:00'
model: gpt-4-1106-preview
summary: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u7DE8\u6210\u3059\u308B\u3068\
  \u306F\u3001\u3042\u306A\u305F\u306E\u30B3\u30FC\u30C9\u3092\u518D\u5229\u7528\u53EF\
  \u80FD\u306A\u30C1\u30E3\u30F3\u30AF\u306B\u5206\u5272\u3059\u308B\u3053\u3068\u3092\
  \u610F\u5473\u3057\u307E\u3059\u3002\u305D\u308C\u305E\u308C\u306E\u30C1\u30E3\u30F3\
  \u30AF\u306F\u7279\u5B9A\u306E\u4ED5\u4E8B\u3092\u884C\u3044\u307E\u3059\u3002\u30D7\
  \u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30B3\u30FC\u30C9\u3092\u8AAD\u307F\u3084\
  \u3059\u304F\u3001\u30C7\u30D0\u30C3\u30B0\u3057\u3084\u3059\u304F\u3001\u518D\u5229\
  \u7528\u3057\u3084\u3059\u304F\u3059\u308B\u305F\u3081\u306B\u3053\u308C\u3092\u884C\
  \u3044\u307E\u3059\u3002\u3053\u308C\u306F\u3001\u4F55\u304B\u3092\u4F5C\u308A\u305F\
  \u3044\u3068\u304D\u306B\u6BCE\u56DE\u30AB\u30AA\u30B9\u306A\u5C71\u304B\u3089\u63A2\
  \u3057\u51FA\u3059\u3053\u3068\u3092\u907F\u3051\u308B\u305F\u3081\u306B\u3001\u30EC\
  \u30B4\u30D6\u30ED\u30C3\u30AF\u3092\u7BB1\u306B\u5206\u985E\u3059\u308B\u3088\u3046\
  \u306A\u3082\u306E\u3067\u3059\u3002."
title: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B"
weight: 18
---

## 方法：
LEDを点滅させたいと想像してください。関数を使わなければ、あなたの`loop`はごちゃごちゃの塊です。関数を使うことで、それは整然とします。こうやってみましょう：

```Arduino
const int LED_PIN = 13;

void setup() {
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  blinkLED(500); // LEDを500ms毎に点滅させる
}

// LEDを点滅させる関数
void blinkLED(int delayTime) {
  digitalWrite(LED_PIN, HIGH);
  delay(delayTime);
  digitalWrite(LED_PIN, LOW);
  delay(delayTime);
}
```

サンプル出力：あなたのLEDは楽しそうに点滅しており、コードの目的が一目で明確です。

## 深掘り
関数が登場する前、プログラミングはスタートからエンドまでごとにある道路旅行でした。関数が登場した後、それは飛行機に飛び乗るようなものになり、重要な部分に直接スキップします。歴史的には、サブルーチン（初期の関数）はプログラミングにおける革命であり、コーダーが自分自身を繰り返すことを避けることを可能にしました — それがDRY原則です、Don’t Repeat Yourself（自分自身を繰り返さない）。関数の代わりとなるものには、マクロやオブジェクト指向プログラミング（OOP）用のクラスの使用が含まれるかもしれません。肝心なこと？関数を定義するとき、コンパイラに対してタスクの実行のための設計図を与えています。Arduinoでは、しばしば単純なコマンドとして機能するvoid関数を定義しますが、関数は値を返すこともでき、より汎用性があります。

## 参照
関数についてもっと知るために、以下を参照してください：

- Arduinoの公式関数リファレンス：https://www.arduino.cc/reference/en/language/functions/
- DRY原則についてもっと学ぶ：https://en.wikipedia.org/wiki/Don%27t_repeat_yourself
- サブルーチンの歴史上のリフレッシャー：https://en.wikipedia.org/wiki/Subroutine
