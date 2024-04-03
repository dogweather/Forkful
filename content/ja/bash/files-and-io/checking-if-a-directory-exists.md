---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:06:53.436767-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:42.394049-06:00'
model: gpt-4-0125-preview
summary: "Bash\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u306B\u304A\u3044\u3066\u3001\
  \u30C7\u30A3\u30EC\u30AF\u30C8\u30EA\u304C\u5B58\u5728\u3059\u308B\u304B\u3092\u78BA\
  \u8A8D\u3059\u308B\u3053\u3068\u306F\u3001\u30D5\u30A1\u30A4\u30EB\u64CD\u4F5C\u3092\
  \u884C\u3046\u524D\u306B\u30C7\u30A3\u30EC\u30AF\u30C8\u30EA\u306E\u5B58\u5728\u3092\
  \u691C\u8A3C\u3059\u308B\u305F\u3081\u306B\u4F7F\u7528\u3055\u308C\u308B\u91CD\u8981\
  \u306A\u5236\u5FA1\u30E1\u30AB\u30CB\u30BA\u30E0\u3067\u3059\u3002\u3053\u306E\u30C1\
  \u30A7\u30C3\u30AF\u306F\u3001\u5B58\u5728\u3057\u306A\u3044\u30C7\u30A3\u30EC\u30AF\
  \u30C8\u30EA\u306B\u30A2\u30AF\u30BB\u30B9\u3057\u305F\u308A\u3001\u5909\u66F4\u3057\
  \u3088\u3046\u3068\u3059\u308B\u3088\u3046\u306A\u30A8\u30E9\u30FC\u3092\u907F\u3051\
  \u308B\u305F\u3081\u306B\u91CD\u8981\u3067\u3042\u308A\u3001\u30B9\u30AF\u30EA\u30D7\
  \u30C8\u306E\u5B9F\u884C\u3092\u3088\u308A\u30B9\u30E0\u30FC\u30BA\u306B\u3001\u4E88\
  \u6E2C\u53EF\u80FD\u306B\u3057\u307E\u3059\u3002."
title: "\u30C7\u30A3\u30EC\u30AF\u30C8\u30EA\u304C\u5B58\u5728\u3059\u308B\u304B\u3069\
  \u3046\u304B\u306E\u78BA\u8A8D"
weight: 20
---

## 方法：
その核となる部分で、Bashは条件文と`-d`オペレーターを使用してディレクトリの存在をチェックすることを可能にします。以下は、このチェックをどのように実行するかを示す簡潔な例です。

```bash
if [ -d "/path/to/directory" ]; then
    echo "ディレクトリは存在します。"
else
    echo "ディレクトリは存在しません。"
fi
```

サンプル出力（ディレクトリが存在する場合）：
```
ディレクトリは存在します。
```

サンプル出力（ディレクトリが存在しない場合）：
```
ディレクトリは存在しません。
```

より複雑なスクリプトでは、存在しない場合にディレクトリを作成するなど、他の操作と組み合わせることが一般的です：

```bash
DIR="/path/to/directory"
if [ -d "$DIR" ]; then
    echo "$DIR は存在します。"
else
    echo "$DIR は存在しません。作成します..."
    mkdir -p "$DIR"
    echo "$DIR を作成しました。"
fi
```

サンプル出力（ディレクトリが存在しない場合、その後作成される）：
```
/path/to/directory は存在しません。作成します...
/path/to/directory を作成しました。
```

Bash自体がこのようなチェックのための強力なツールを提供しているため、ディレクトリの存在検証のために、特に人気のあるサードパーティ製のライブラリは存在しません。ネイティブのBashコマンドは、このタスクのために完全に有能で効率的です。
