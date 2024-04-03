---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:10:39.361199-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:42.451268-06:00'
model: gpt-4-0125-preview
summary: "PowerShell\u3067\u73FE\u5728\u306E\u65E5\u4ED8\u3092\u53D6\u5F97\u3059\u308B\
  \u3053\u3068\u306F\u3001\u30B7\u30B9\u30C6\u30E0\u306E\u73FE\u5728\u306E\u65E5\u4ED8\
  \u3068\u6642\u523B\u3092\u53D6\u5F97\u3059\u308B\u3053\u3068\u306B\u3064\u3044\u3066\
  \u3067\u3059\u3002\u3053\u306E\u64CD\u4F5C\u306F\u3001\u30ED\u30B0\u53D6\u308A\u3001\
  \u30BF\u30A4\u30DF\u30F3\u30B0\u64CD\u4F5C\u3001\u307E\u305F\u306F\u65E5\u4ED8\u306B\
  \u57FA\u3065\u3044\u3066\u610F\u601D\u6C7A\u5B9A\u3092\u884C\u3046\u306A\u3069\u306E\
  \u30BF\u30B9\u30AF\u306B\u3068\u3063\u3066\u57FA\u672C\u7684\u306A\u3082\u306E\u3067\
  \u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30A4\u30D9\u30F3\u30C8\
  \u3092\u8FFD\u8DE1\u3057\u3001\u30BF\u30B9\u30AF\u3092\u30B9\u30B1\u30B8\u30E5\u30FC\
  \u30EB\u3057\u3001\u30B9\u30AF\u30EA\u30D7\u30C8\u3084\u30A2\u30D7\u30EA\u30B1\u30FC\
  \u30B7\u30E7\u30F3\u3067\u65E5\u4ED8\u56FA\u6709\u306E\u30ED\u30B8\u30C3\u30AF\u3092\
  \u6271\u3046\u305F\u3081\u306B\u3053\u306E\u6A5F\u80FD\u3092\u4F7F\u7528\u3057\u307E\
  \u3059\u3002."
title: "\u73FE\u5728\u306E\u65E5\u4ED8\u306E\u53D6\u5F97"
weight: 29
---

## 方法:
PowerShellは、日付と時刻を取得するための直感的なコマンドレットを提供しています。`Get-Date` コマンドレットは、この目的のための主要なツールです。必要に応じてフォーマットや操作を行うことができる、完全な日付と時刻を返します。

```powershell
# 現在の日付と時刻を取得
Get-Date
```

**サンプル出力:**

```
2023年9月5日 火曜日 9:46:02 AM
```

出力をフォーマットして、必要な情報のみを表示することもできます。例えば、日付のみや時間のみです。

```powershell
# 特定のフォーマットで現在の日付のみを取得
Get-Date -Format "yyyy-MM-dd"
```

**サンプル出力:**

```
2023-09-05
```

```powershell
# 現在の時刻のみを取得
Get-Date -Format "HH:mm:ss"
```

**サンプル出力:**

```
09:46:02
```

### .NETクラスの使用
PowerShellは.NETクラスに直接アクセスを許可し、日付と時刻を扱う別の方法を提供します。

```powershell
# .NET DateTimeクラスを使用して現在の日付と時刻を取得
[System.DateTime]::Now
```

**サンプル出力:**

```
2023年9月5日 火曜日 9:46:02 AM
```

UTC時刻の場合:

```powershell
# .NET DateTimeクラスを使用して現在のUTC日付と時刻を取得
[System.DateTime]::UtcNow
```

**サンプル出力:**

```
2023年9月5日 火曜日 1:46:02 PM
```

これらのコマンドとクラスは、PowerShellでの日付と時刻の操作を強力かつ柔軟に行うためのものであり、多くのスクリプティングや自動化タスクに不可欠です。
