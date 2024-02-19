---
aliases:
- /ja/python/refactoring/
date: 2024-01-26 03:37:35.850322-07:00
description: "\u30EA\u30D5\u30A1\u30AF\u30BF\u30EA\u30F3\u30B0\u306F\u3001\u65E2\u5B58\
  \u306E\u30B3\u30F3\u30D4\u30E5\u30FC\u30BF\u30FC\u30B3\u30FC\u30C9\u306E\u69CB\u9020\
  \u3092\u5909\u66F4\u3059\u308B\u30D7\u30ED\u30BB\u30B9\u2014\u30D5\u30A1\u30AF\u30BF\
  \u30EA\u30F3\u30B0\u3092\u5909\u66F4\u3059\u308B\u2014\u3067\u3042\u308A\u306A\u304C\
  \u3089\u3001\u305D\u306E\u5916\u90E8\u7684\u306A\u632F\u308B\u821E\u3044\u3092\u5909\
  \u3048\u306A\u3044\u3053\u3068\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\
  \u306F\u30B3\u30FC\u30C9\u3092\u6574\u7406\u3057\u3001\u53EF\u8AAD\u6027\u3092\u5411\
  \u4E0A\u3055\u305B\u3001\u65B0\u3057\u3044\u6A5F\u80FD\u3092\u8FFD\u52A0\u3059\u308B\
  \u3053\u3068\u306A\u304F\u3001\u4FDD\u5B88\u3084\u62E1\u5F35\u3092\u5BB9\u6613\u306B\
  \u3059\u308B\u305F\u3081\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:54.571629
model: gpt-4-0125-preview
summary: "\u30EA\u30D5\u30A1\u30AF\u30BF\u30EA\u30F3\u30B0\u306F\u3001\u65E2\u5B58\
  \u306E\u30B3\u30F3\u30D4\u30E5\u30FC\u30BF\u30FC\u30B3\u30FC\u30C9\u306E\u69CB\u9020\
  \u3092\u5909\u66F4\u3059\u308B\u30D7\u30ED\u30BB\u30B9\u2014\u30D5\u30A1\u30AF\u30BF\
  \u30EA\u30F3\u30B0\u3092\u5909\u66F4\u3059\u308B\u2014\u3067\u3042\u308A\u306A\u304C\
  \u3089\u3001\u305D\u306E\u5916\u90E8\u7684\u306A\u632F\u308B\u821E\u3044\u3092\u5909\
  \u3048\u306A\u3044\u3053\u3068\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\
  \u306F\u30B3\u30FC\u30C9\u3092\u6574\u7406\u3057\u3001\u53EF\u8AAD\u6027\u3092\u5411\
  \u4E0A\u3055\u305B\u3001\u65B0\u3057\u3044\u6A5F\u80FD\u3092\u8FFD\u52A0\u3059\u308B\
  \u3053\u3068\u306A\u304F\u3001\u4FDD\u5B88\u3084\u62E1\u5F35\u3092\u5BB9\u6613\u306B\
  \u3059\u308B\u305F\u3081\u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002"
title: "\u30EA\u30D5\u30A1\u30AF\u30BF\u30EA\u30F3\u30B0"
---

{{< edit_this_page >}}

## 何となぜ？
リファクタリングは、既存のコンピューターコードの構造を変更するプロセス—ファクタリングを変更する—でありながら、その外部的な振る舞いを変えないことです。プログラマーはコードを整理し、可読性を向上させ、新しい機能を追加することなく、保守や拡張を容易にするためにこれを行います。

## 方法
たとえば、長さと幅が与えられた矩形の面積と周囲を計算して印刷するコードの塊があったとします。それは仕事をしますが、繰り返しで少し雑然としています。

```python
# オリジナルバージョン
length = 4
width = 3

# 面積と周囲を計算
area = length * width
perimeter = 2 * (length + width)

print("面積:", area)
print("周囲:", perimeter)
```

機能を関数にカプセル化することで、このコードをリファクタリングできます。これにより、コードはより整理され再利用可能になります：

```python
# リファクタリングバージョン

def calculate_area(length, width):
    return length * width

def calculate_perimeter(length, width):
    return 2 * (length + width)

# 使用法
length = 4
width = 3

print("面積:", calculate_area(length, width))
print("周囲:", calculate_perimeter(length, width))
```

両方のスニペットは同じ結果を出力します：
```
面積: 12
周囲: 14
```

しかし、リファクタリングされたバージョンはよりクリーンで関心を分離しており、一方の計算を更新しても他方に影響を与えずに済むようにします。

## 深掘り
リファクタリングは、プログラマーがコードが「動作中」であっても改善できる、そしてすべきであることに気づいたソフトウェア工学の初期の日々にルーツがあります。マーティン・ファウラーの画期的な書籍「リファクタリング：既存のコードの設計を改善する」は、多くの核心原則と技術を明確に述べました。彼は有名に「どんな愚か者でもコンピュータが理解できるコードを書ける。良いプログラマは人間が理解できるコードを書く」と言いました。

リファクタリングの代替手段には、ゼロからコードを書き直すことや、体系的な改善なしに小規模な調整を加えることが含まれます。しかし、リファクタリングは通常、書き直しよりもコスト効果が高く、アドホックな修正よりもリスクが低いです。実装の詳細は各プログラミングパラダイムに固有のものかもしれませんが、オブジェクト指向プログラミングは、特に関数の抽出（私たちの`calculate_area`関数と`calculate_perimeter`関数のような）、インライン化、オブジェクト間での機能の移動、そして明確性のためのメソッドや変数の名前の変更などの技術で、リファクタリングに特に適しています。

Pythonでのリファクタリングは、組み込みのリファクタリング能力を備えた`PyCharm`や、リファクタリングに特化して設計されたPythonライブラリである`rope`などのツールをよく使用します。リファクタリング中には、`git`のようなバージョン管理を注意深く使用し、変更を段階的に追跡することが強く推奨されます。

## 参照
もっと詳しく知りたい方は、以下のリソースをご覧ください：
- マーティン・ファウラーの本：[リファクタリング：既存のコードの設計を改善する](http://www.refactoring.com/)
- Pythonでのリファクタリング `rope`：[GitHub - rope](https://github.com/python-rope/rope)
- PyCharm リファクタリングドキュメント：[Jetbrains PyCharm リファクタリングソースコード](https://www.jetbrains.com/help/pycharm/refactoring-source-code.html)
- Refactoring.guru：[リファクタリングとデザインパターン](https://refactoring.guru/refactoring)
- Uncle Bob（ロバートC.マーティン）によるクリーンコード講義：[クリーンコード - Uncle Bob / レッスン 1](https://www.youtube.com/watch?v=7EmboKQH8lM)
