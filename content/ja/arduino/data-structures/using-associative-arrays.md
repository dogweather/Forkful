---
aliases:
- /ja/arduino/using-associative-arrays/
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:20.984580-07:00
description: "Arduino\u306E\u4E16\u754C\u3067\u306F\u3001\u9023\u60F3\u914D\u5217\u3092\
  \u4F7F\u3063\u3066\u30AD\u30FC\u3068\u5024\u3092\u30DA\u30A2\u306B\u3059\u308B\u3053\
  \u3068\u304C\u3067\u304D\u3001\u3053\u308C\u306F\u307E\u308B\u3067\u9774\u4E0B\u3092\
  \u30DA\u30A2\u306B\u3059\u308B\u3088\u3046\u306A\u3082\u306E\u3067\u3059\u3002\u8A18\
  \u8FF0\u7684\u306A\u540D\u524D\u3092\u4F7F\u3063\u3066\u30C7\u30FC\u30BF\u3092\u4FDD\
  \u5B58\u30FB\u53D6\u5F97\u3059\u308B\u5FC5\u8981\u304C\u3042\u308B\u5834\u5408\u306B\
  \u3001\u30B3\u30FC\u30C9\u3092\u3088\u308A\u30AF\u30EA\u30FC\u30F3\u3067\u7406\u89E3\
  \u3057\u3084\u3059\u304F\u3059\u308B\u305F\u3081\u306E\u9078\u629E\u80A2\u3068\u306A\
  \u308A\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:55.146606
model: gpt-4-0125-preview
summary: "Arduino\u306E\u4E16\u754C\u3067\u306F\u3001\u9023\u60F3\u914D\u5217\u3092\
  \u4F7F\u3063\u3066\u30AD\u30FC\u3068\u5024\u3092\u30DA\u30A2\u306B\u3059\u308B\u3053\
  \u3068\u304C\u3067\u304D\u3001\u3053\u308C\u306F\u307E\u308B\u3067\u9774\u4E0B\u3092\
  \u30DA\u30A2\u306B\u3059\u308B\u3088\u3046\u306A\u3082\u306E\u3067\u3059\u3002\u8A18\
  \u8FF0\u7684\u306A\u540D\u524D\u3092\u4F7F\u3063\u3066\u30C7\u30FC\u30BF\u3092\u4FDD\
  \u5B58\u30FB\u53D6\u5F97\u3059\u308B\u5FC5\u8981\u304C\u3042\u308B\u5834\u5408\u306B\
  \u3001\u30B3\u30FC\u30C9\u3092\u3088\u308A\u30AF\u30EA\u30FC\u30F3\u3067\u7406\u89E3\
  \u3057\u3084\u3059\u304F\u3059\u308B\u305F\u3081\u306E\u9078\u629E\u80A2\u3068\u306A\
  \u308A\u307E\u3059\u3002"
title: "\u9023\u60F3\u914D\u5217\u306E\u4F7F\u7528"
---

{{< edit_this_page >}}

## 何となぜ？
Arduinoの世界では、連想配列を使ってキーと値をペアにすることができ、これはまるで靴下をペアにするようなものです。記述的な名前を使ってデータを保存・取得する必要がある場合に、コードをよりクリーンで理解しやすくするための選択肢となります。

## 方法：
厳密に言えば、Arduinoには高レベル言語に見られるような組み込みの連想配列のサポートはありません。しかし、恐れることはありません。構造体や配列を使用してこの機能を模倣するクラフト的な方法があります。ここでは、異なる都市の温度を保存およびアクセスするための基本的な「連想配列」を作成するための簡単な例を紹介します。

まず、都市（キー）とその温度（値）を保持するための構造体を定義します：

```cpp
struct CityTemperature {
  String city;
  float temperature;
};
```

次に、`CityTemperature`オブジェクトの配列を初期化します：

```cpp
CityTemperature temperatures[] = {
  {"New York", 19.5},
  {"Los Angeles", 22.0},
  {"Chicago", 17.0}
};
```

特定の都市の温度にアクセスして表示する方法は次のとおりです：

```cpp
void setup() {
  Serial.begin(9600);
  for(int i = 0; i < 3; i++) {
    if(temperatures[i].city == "Los Angeles") {
      Serial.print("The temperature in Los Angeles is: ");
      Serial.println(temperatures[i].temperature);
    }
  }
}

void loop() {
  // 今はここに何もない。
}
```

このコードを実行すると、次の出力が得られます：

```
The temperature in Los Angeles is: 22.0
```

## 詳細な調査
歴史的に、CおよびC++(Arduinoの構文が派生している言語)には組み込みの連想配列がなく、上に示したような回避策が必要でした。このアプローチは比較的シンプルですが、データサイズが増加するにつれてO(n)の検索時間のためにスケーラビリティが低下します。

Pythonのような言語は辞書を提供し、JavaScriptにはこの目的のためのオブジェクトがあり、いずれもキー-値ペアを管理するにははるかに効率的です。Arduinoでパフォーマンスと効率が重要になったとき、開発者はライブラリを介して実装されるハッシュテーブルなどのより専門的なデータ構造を選択するかもしれません。

Arduinoがネイティブに連想配列をサポートしていなくても、`HashMap`のようなライブラリをプロジェクトに追加して同様の機能をDIYアプローチよりも優れたパフォーマンスで提供できるように開発されたコミュニティがあります。これらのライブラリは、特に複雑なプロジェクトのために、連想配列を管理するよりエレガントで効率的な手段を通常提供します。
