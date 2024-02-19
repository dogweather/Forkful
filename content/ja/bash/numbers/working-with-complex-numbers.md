---
aliases:
- /ja/bash/working-with-complex-numbers/
date: 2024-01-26 04:36:52.254965-07:00
description: "\u8907\u7D20\u6570\u306F\u5B9F\u90E8\u3068\u865A\u90E8\u3067\u69CB\u6210\
  \u3055\u308C\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u901A\
  \u5E38\u306E\u5B9F\u6570\u3067\u306F\u4E0D\u5341\u5206\u306A\u5834\u5408\u3001\u4FE1\
  \u53F7\u51E6\u7406\u3001\u91CF\u5B50\u529B\u5B66\u3001\u307E\u305F\u4ED6\u306E\u8A08\
  \u7B97\u304C\u5FC5\u8981\u306A\u5834\u9762\u3067\u3053\u308C\u3092\u4F7F\u7528\u3057\
  \u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:55.067135
model: gpt-4-0125-preview
summary: "\u8907\u7D20\u6570\u306F\u5B9F\u90E8\u3068\u865A\u90E8\u3067\u69CB\u6210\
  \u3055\u308C\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u901A\
  \u5E38\u306E\u5B9F\u6570\u3067\u306F\u4E0D\u5341\u5206\u306A\u5834\u5408\u3001\u4FE1\
  \u53F7\u51E6\u7406\u3001\u91CF\u5B50\u529B\u5B66\u3001\u307E\u305F\u4ED6\u306E\u8A08\
  \u7B97\u304C\u5FC5\u8981\u306A\u5834\u9762\u3067\u3053\u308C\u3092\u4F7F\u7528\u3057\
  \u307E\u3059\u3002"
title: "\u8907\u7D20\u6570\u306E\u6271\u3044\u65B9"
---

{{< edit_this_page >}}

## 何となぜ？
複素数は実部と虚部で構成されます。プログラマーは、通常の実数では不十分な場合、信号処理、量子力学、また他の計算が必要な場面でこれを使用します。

## 方法：
Bashはネイティブに複素数をサポートしていません。よく`bc`コマンドとその`-l`オプションを使用します。以下はbashで複素数を処理する方法です：

```bash
echo "sqrt(-1)" | bc -l
```

出力：
```bash
j
```

乗算：

```bash
echo "(-1 + -1i) * (4 + 3i)" | bc -l
```

出力：
```bash
-1.00000000000000000000-7.00000000000000000000i
```

## 深掘り
複素数は16世紀から存在していますが、Bashのようなスクリプト言語は、標準では複素数のような数学的計算には向いていません。そのため、`bc`や`awk`のようなツールがよく利用されます。複素数の処理に適した他の言語には、より高度な数学的機能を備えたPythonの`cmath`モジュールやMATLABがあります。Bashにとっては、ツールを活用することがすべてです - `bc`は虚数単位を表すために小文字の'i'を使用し、足し算、引き算、掛け算、割り算などの基本的な操作をサポートしています。

## 参照
- `bc`マニュアル：https://www.gnu.org/software/bc/manual/html_mono/bc.html
- GNU Octave（MATLABの代替品）：https://www.gnu.org/software/octave/
- Python `cmath`モジュール：https://docs.python.org/3/library/cmath.html
