---
aliases:
- /ja/google-apps-script/using-associative-arrays/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:04:18.248544-07:00
description: "\u9023\u60F3\u914D\u5217\u306F\u3001Google Apps\u2026"
lastmod: 2024-02-18 23:08:54.515051
model: gpt-4-0125-preview
summary: "\u9023\u60F3\u914D\u5217\u306F\u3001Google Apps\u2026"
title: "\u9023\u60F3\u914D\u5217\u306E\u4F7F\u7528"
---

{{< edit_this_page >}}

## 何を、なぜ？

連想配列は、Google Apps Script（JavaScriptのバリアント）ではオブジェクトとして知られており、プログラマーがキーと値のペアのコレクションを作成することを可能にします。この機能は特に、動的に名付けられたプロパティを扱う場合や、従来の配列の線形ストレージやアクセスモデルが不十分な場合に、データを効率的に格納および操作するために重要です。

## 方法：

Google Apps Scriptで連想配列（オブジェクト）を作成および操作するには、中カッコ `{}` を使用してキーバリューペアを定義します。キーは一意の識別子であり、値は文字列や数値から、より複雑なオブジェクトや関数まで何でもかまいません。基本的な例を以下に示します：

```javascript
function createAssociativeArray() {
  var user = {
    name: "John Doe",
    age: 30,
    email: "johndoe@example.com"
  };

  // 値へのアクセス
  Logger.log(user.name); // 出力: John Doe
  Logger.log(user["email"]); // 出力: johndoe@example.com

  // 新しいキーバリューペアの追加
  user.title = "Software Developer";
  user["country"] = "USA";

  Logger.log(user.title); // 出力: Software Developer

  // キーバリューペアの反復処理
  for (var key in user) {
    Logger.log(key + ': ' + user[key]);
  }
}
```

反復部分のサンプル出力は次のようになるかもしれません：
```
name: John Doe
age: 30
email: johndoe@example.com
title: Software Developer
country: USA
```

プロパティへのアクセスや設定にドット表記やブラケット表記の両方を使用できることに注目してください。ブラケット表記は、特にキーが動的に決定されたものや識別子で許可されていない文字を含む場合に便利です。

## 深掘り

オブジェクトの形式での連想配列は、JavaScriptのプロトタイプベースの継承メカニズムを反映しており、JavaScriptおよび拡張としてのGoogle Apps Scriptの基石となっています。従来の連想配列や辞書（例えばPythonのdict）を持つ言語とは異なり、Google Apps Scriptのオブジェクトは、JavaScriptの動的な性質から得られる柔軟で強力な手段でデータを構造化することを可能にします。

ただし、ECMAScript 2015の仕様が`Map`および`Set`オブジェクトを導入し、挿入順の維持や大規模なデータセットに対するパフォーマンスの向上など、オブジェクトに比べて一部の利点を持つより直接的な連想コレクションの取り扱いを提供したことは重要です。Google Apps Scriptもこれらをサポートしていますが、オブジェクトを使用するか、新しい`Map`/`Set`構造を使用するかの選択は、特定のニーズとパフォーマンスの考慮事項に依存します。ほとんどの連想配列のタスクには、従来のオブジェクトベースの実装が親しみやすく多用途なアプローチを提供しますが、スクリプトの複雑さが増すにつれて、新しい代替手段を検討することが望ましいです。
