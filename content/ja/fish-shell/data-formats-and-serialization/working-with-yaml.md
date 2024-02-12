---
title:                "YAML を操作する"
aliases:
- /ja/fish-shell/working-with-yaml/
date:                  2024-02-03T19:25:41.306129-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML を操作する"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/fish-shell/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 何となぜ？
YAMLを操作するとは、設定ファイル用のデータ直列化フォーマットであるYAML（YAML Ain't Markup Language）ファイルをパーシングし、Fish Shell内で操作することを意味します。プログラマーはこれを行うことで、シェル環境の文脈内でアプリケーションやサービスを効率よく自動化、設定することができ、構成管理やリソースのプロビジョニングといったタスクを容易にします。

## どのようにして：
Fish ShellにはYAMLをパーシングするための組み込みサポートはありませんが、`yq`（軽量でポータブルなコマンドラインYAMLプロセッサ）といったサードパーティツールを利用することでYAMLデータを扱うことができます。

**yqのインストール（まだインストールされていない場合）：**
```fish
sudo apt-get install yq
```

**YAMLファイルから値を読み取る：**
次の内容を持つYAMLファイル`config.yaml`があるとします：
```yaml
database:
  host: localhost
  port: 3306
```

データベースホストを読み取るには、次を使用します：
```fish
set host (yq e '.database.host' config.yaml)
echo $host
```
**サンプル出力：**
```
localhost
```

**YAMLファイル内の値を更新する：**
`port`を`5432`に更新するには、次を使用します：
```fish
yq e '.database.port = 5432' -i config.yaml
```
**更新を確認する：**
```fish
yq e '.database.port' config.yaml
```
**サンプル出力：**
```
5432
```

**新しいYAMLファイルを書き込む：**
事前定義された内容で新しい`new_config.yaml`を作成するには：
```fish
echo "webserver:
  host: '127.0.0.1'
  port: 8080" | yq e -P - > new_config.yaml
```
この操作は`yq`を使用して、文字列を新しいYAMLファイルに処理し、きれいに印刷（-Pフラグ）します。

**複雑な構造をパーシングする：**
より複雑なYAMLファイルを扱い、ネストされた配列やオブジェクトを取得する必要がある場合、次を実行できます：
```fish
echo "servers:
  - name: server1
    ip: 192.168.1.101
  - name: server2
    ip: 192.168.1.102" > servers.yaml

yq e '.servers[].name' servers.yaml
```
**サンプル出力：**
```
server1
server2
```
`yq`を使用して、Fish ShellはYAMLドキュメントを通して効率的にナビゲートし、さまざまな自動化や設定タスクのためにそれらを操作することを簡単にします。
