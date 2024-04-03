---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:29.459544-07:00
description: "Fish\u2026"
lastmod: '2024-03-13T22:44:42.756765-06:00'
model: gpt-4-0125-preview
summary: "Fish Shell\u3067\u30C7\u30A3\u30EC\u30AF\u30C8\u30EA\u304C\u5B58\u5728\u3059\
  \u308B\u304B\u3092\u78BA\u8A8D\u3059\u308B\u3053\u3068\u306F\u3001\u30C7\u30A3\u30EC\
  \u30AF\u30C8\u30EA\u69CB\u9020\u306E\u5B58\u5728\u3084\u4E0D\u5728\u306B\u57FA\u3065\
  \u3044\u3066\u30B9\u30AF\u30EA\u30D7\u30C8\u304C\u5224\u65AD\u3092\u884C\u3046\u3053\
  \u3068\u3092\u53EF\u80FD\u306B\u3057\u3001\u6761\u4EF6\u4ED8\u304D\u30D5\u30A1\u30A4\
  \u30EB\u64CD\u4F5C\u3001\u30ED\u30B0\u8A18\u9332\u3001\u307E\u305F\u306F\u74B0\u5883\
  \u8A2D\u5B9A\u306E\u3088\u3046\u306A\u30BF\u30B9\u30AF\u3092\u53EF\u80FD\u306B\u3057\
  \u307E\u3059\u3002\u3053\u306E\u6280\u8853\u306F\u3001\u30D5\u30A1\u30A4\u30EB\u30B7\
  \u30B9\u30C6\u30E0\u3068\u4E88\u6E2C\u53EF\u80FD\u306A\u65B9\u6CD5\u3067\u3084\u308A\
  \u53D6\u308A\u3059\u308B\u5805\u7262\u306A\u30B9\u30AF\u30EA\u30D7\u30C8\u3092\u66F8\
  \u304F\u305F\u3081\u306B\u306F\u6B20\u304B\u305B\u307E\u305B\u3093\u3002."
title: "\u30C7\u30A3\u30EC\u30AF\u30C8\u30EA\u304C\u5B58\u5728\u3059\u308B\u304B\u3069\
  \u3046\u304B\u306E\u78BA\u8A8D"
weight: 20
---

## 方法：
Fish Shellは`test`コマンドを使ってファイルタイプや特性をチェックします。これには、対象がディレクトリかどうかを含みます。ディレクトリが存在するかを確認する基本的な方法は以下のとおりです：

```fish
if test -d /path/to/dir
    echo "ディレクトリは存在します"
else
    echo "ディレクトリは存在しません"
end
```
サンプル出力：
```
ディレクトリは存在します
```

より合理化されたファイルやディレクトリ操作には、`fd`のような外部ツールを使うこともありますが、これは存在を単にチェックするよりも、ファイルやディレクトリを見つけるためによく使われます。しかし、Fishスクリプティングと組み合わせることで便利な結果が得られます：

```fish
set dir "/path/to/search"
if fd . $dir --type directory --max-depth 1 | grep -q $dir
    echo "ディレクトリは存在します"
else
    echo "ディレクトリは存在しません"
end
```

この`fd`の例では、指定した深さでディレクトリを検索し、`grep`が一致をチェックします。これは洗練されたチェックに対して多用途です。しかし、存在を直接確認する目的には、Fishのビルトイン`test`を使うことが、効率的で明快です。
