---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:53.705967-07:00
description: "YAML\u306F\u3001\u300CYAML Ain't Markup\u2026"
lastmod: '2024-03-13T22:44:42.402660-06:00'
model: gpt-4-0125-preview
summary: "YAML\u306F\u3001\u300CYAML Ain't Markup Language\u300D\u3092\u610F\u5473\
  \u3057\u3001\u4EBA\u9593\u304C\u8AAD\u307F\u66F8\u304D\u53EF\u80FD\u306A\u30C7\u30FC\
  \u30BF\u30B7\u30EA\u30A2\u30E9\u30A4\u30BC\u30FC\u30B7\u30E7\u30F3\u6A19\u6E96\u3067\
  \u3001\u8A2D\u5B9A\u30D5\u30A1\u30A4\u30EB\u3084\u30C7\u30FC\u30BF\u306E\u4FDD\u5B58\
  \u3084\u8EE2\u9001\u304C\u884C\u308F\u308C\u308B\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\
  \u30E7\u30F3\u3067\u4F7F\u7528\u3059\u308B\u3053\u3068\u304C\u3067\u304D\u307E\u3059\
  \u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001YAML\u306E\u660E\u5FEB\u3055\
  \u3068\u5358\u7D14\u3055\u3001\u7279\u306B\u8907\u96D1\u306A\u8A2D\u5B9A\u3084\u7C21\
  \u5358\u306B\u7DE8\u96C6\u53EF\u80FD\u306A\u30C7\u30FC\u30BF\u69CB\u9020\u304C\u5FC5\
  \u8981\u306A\u30D7\u30ED\u30B8\u30A7\u30AF\u30C8\u306B\u304A\u3044\u3066\u3001YAML\u3092\
  \u597D\u3093\u3067\u4F7F\u7528\u3057\u307E\u3059\u3002."
title: "YAML \u3092\u64CD\u4F5C\u3059\u308B"
weight: 41
---

## 使い方:
Bashで直接YAMLを扱うには、BashにはYAMLの解析をサポートする機能が組み込まれていないため、ちょっとした工夫が必要です。しかし、`yq`のような外部ツール（軽量でポータブルなコマンドラインYAMLプロセッサ）を使用して、効率的にYAMLファイルとやり取りすることができます。いくつかの一般的な操作を見てみましょう：

### `yq`のインストール:
例に入る前に、`yq`がインストールされていることを確認してください。たいていの場合、パッケージマネージャーからインストールできます。例えば、Ubuntuの場合：

```bash
sudo apt-get install yq
```

または、GitHubリポジトリから直接ダウンロードすることもできます。

### 値の読み取り:
`config.yaml`という名前のファイルがあり、以下の内容が含まれているとします：

```yaml
database:
  host: localhost
  port: 5432
user:
  name: admin
  password: secret
```

データベースのホストを読み取るには、次のように`yq`を使用します：

```bash
yq e '.database.host' config.yaml
```

**サンプル出力:**

```
localhost
```

### 値の更新:
`config.yaml`のユーザー名を更新するには、`-i`（インプレース）オプションを付けて`yq eval`コマンドを使用します：

```bash
yq e '.user.name = "newadmin"' -i config.yaml
```

次で変更を確認します：

```bash
yq e '.user.name' config.yaml
```

**サンプル出力:**

```
newadmin
```

### 新しい要素の追加:
データベースセクションに、新たなフィールド`timeout`を追加するには：

```bash
yq e '.database.timeout = 30' -i config.yaml
```

ファイルの内容を確認すると、追加されていることが確認できます。

### 要素の削除:
ユーザーのパスワードを削除するには：

```bash
yq e 'del(.user.password)' -i config.yaml
```

この操作により、設定からパスワードフィールドが削除されます。

`yq`は強力なツールであり、YAMLをJSONに変換する、ファイルをマージする、さらに複雑な操作を行うなど、さらに多くの機能を持っています。さらに探求するためには、`yq`のドキュメントを参照してください。
