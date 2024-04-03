---
date: 2024-01-27 20:35:24.495195-07:00
description: "\u4E71\u6570\u306E\u751F\u6210\u306B\u306F\u3001\u30B7\u30DF\u30E5\u30EC\
  \u30FC\u30B7\u30E7\u30F3\u3001\u30B2\u30FC\u30E0\u3001\u30BB\u30AD\u30E5\u30EA\u30C6\
  \u30A3\u30A2\u30EB\u30B4\u30EA\u30BA\u30E0\u306E\u958B\u767A\u306B\u4E0D\u53EF\u6B20\
  \u3067\u3042\u308A\u3001\u5076\u7136\u3088\u308A\u3082\u5408\u7406\u7684\u306B\u4E88\
  \u6E2C\u3059\u308B\u3053\u3068\u304C\u3067\u304D\u306A\u3044\u6570\u3092\u4F5C\u308A\
  \u51FA\u3059\u3053\u3068\u304C\u542B\u307E\u308C\u307E\u3059\u3002\u30D7\u30ED\u30B0\
  \u30E9\u30DE\u30FC\u306F\u3001\u4E0D\u78BA\u5B9A\u6027\u3092\u5C0E\u5165\u3059\u308B\
  \u304B\u3001\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u3067\u5B9F\u4E16\u754C\
  \u306E\u73FE\u8C61\u3092\u30B7\u30DF\u30E5\u30EC\u30FC\u30C8\u3059\u308B\u305F\u3081\
  \u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:41.494792-06:00'
model: gpt-4-0125-preview
summary: "\u4E71\u6570\u306E\u751F\u6210\u306B\u306F\u3001\u30B7\u30DF\u30E5\u30EC\
  \u30FC\u30B7\u30E7\u30F3\u3001\u30B2\u30FC\u30E0\u3001\u30BB\u30AD\u30E5\u30EA\u30C6\
  \u30A3\u30A2\u30EB\u30B4\u30EA\u30BA\u30E0\u306E\u958B\u767A\u306B\u4E0D\u53EF\u6B20\
  \u3067\u3042\u308A\u3001\u5076\u7136\u3088\u308A\u3082\u5408\u7406\u7684\u306B\u4E88\
  \u6E2C\u3059\u308B\u3053\u3068\u304C\u3067\u304D\u306A\u3044\u6570\u3092\u4F5C\u308A\
  \u51FA\u3059\u3053\u3068\u304C\u542B\u307E\u308C\u307E\u3059\u3002\u30D7\u30ED\u30B0\
  \u30E9\u30DE\u30FC\u306F\u3001\u4E0D\u78BA\u5B9A\u6027\u3092\u5C0E\u5165\u3059\u308B\
  \u304B\u3001\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u3067\u5B9F\u4E16\u754C\
  \u306E\u73FE\u8C61\u3092\u30B7\u30DF\u30E5\u30EC\u30FC\u30C8\u3059\u308B\u305F\u3081\
  \u306B\u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002."
title: "\u4E71\u6570\u306E\u751F\u6210"
weight: 12
---

## どのようにして：
Pythonは、さまざまな用途のための乱数を生成するのに役立つ`random`モジュールを提供しています。以下の方法で始めることができます：

1. **モジュールのインポート**
    ```Python
    import random
    ```

2. **ランダムな整数の生成**
    任意の二つの数の間で。
    ```Python
    random_integer = random.randint(1, 10)
    print(random_integer)
    ```
    サンプル出力: `7`

3. **浮動小数点数の生成**
    0と1の間で。
    ```Python
    random_float = random.random()
    print(random_float)
    ```
    サンプル出力: `0.436432634653`

    異なる範囲で浮動小数点数が必要な場合、乗算します：
    ```Python
    random_float_range = random.random() * 5  # 0から5まで
    print(random_float_range)
    ```
    サンプル出力: `3.182093745`

4. **リストからランダムな要素を選択する**
    ```Python
    greetings = ['Hello', 'Hi', 'Hey', 'Hola', 'Bonjour']
    print(random.choice(greetings))
    ```
    サンプル出力: `Hola`

5. **リストをシャッフルする**
    カードゲームや順序をランダム化する必要があるあらゆるアプリケーションに最適です。
    ```Python
    numbers = list(range(10))
    random.shuffle(numbers)
    print(numbers)
    ```
    サンプル出力: `[2, 5, 0, 4, 9, 8, 1, 7, 6, 3]`

## 詳細な解説
Pythonの`random`モジュールは擬似乱数生成器（PRNG）を使用しており、具体的にはメルセンヌ・ツイスタアルゴリズムを使用しています。これは一般的なアプリケーションには適していますが、十分な出力を観測することで予測可能であるため、暗号学的な目的には不向きです。Python 3.6で導入された`secrets`モジュールは、セキュリティに敏感なアプリケーションで暗号学的に強固な乱数を生成するためのより良い代替手段を提供します。例えば、パスワードリセットリンクのための安全なランダムトークンを生成する場合：

```Python
import secrets
token = secrets.token_hex(16)
print(token)
```

歴史的に、真にランダムな数を生成することは、物理現象や手動で入力されたシードに依存する初期の方法を含め、コンピューティングにおいて挑戦でした。メルセンヌ・ツイスタ（少なくとも2023年の私の最後の知識更新時点でPythonの`random`モジュールでデフォルトで使用されている）のようなアルゴリズムの開発と採用は、顕著な進歩を示しました。しかし、より安全で効率的なアルゴリズムを求める継続的な探求は、暗号関連のタスクのために`secrets`モジュールを含むに至りました。この進化は、ソフトウェア開発におけるセキュリティの重要性の高まりと、暗号化から安全なトークン生成に至るまでのアプリケーションにおけるより強固な乱数の必要性を反映しています。
