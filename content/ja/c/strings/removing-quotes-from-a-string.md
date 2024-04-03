---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:07:29.951272-07:00
description: "C\u8A00\u8A9E\u3067\u6587\u5B57\u5217\u304B\u3089\u5F15\u7528\u7B26\u3092\
  \u524A\u9664\u3059\u308B\u3068\u306F\u3001\u5358\u4E00\uFF08' '\uFF09\u307E\u305F\
  \u306F\u4E8C\u91CD\uFF08\"\u2026"
lastmod: '2024-03-13T22:44:42.779743-06:00'
model: gpt-4-0125-preview
summary: "C\u8A00\u8A9E\u3067\u6587\u5B57\u5217\u304B\u3089\u5F15\u7528\u7B26\u3092\
  \u524A\u9664\u3059\u308B\u3068\u306F\u3001\u5358\u4E00\uFF08' '\uFF09\u307E\u305F\
  \u306F\u4E8C\u91CD\uFF08\" \"\uFF09\u306E\u5F15\u7528\u7B26\u3067\u56F2\u307E\u308C\
  \u305F\u30C6\u30AD\u30B9\u30C8\u30B3\u30F3\u30C6\u30F3\u30C4\u3092\u62BD\u51FA\u3059\
  \u308B\u3053\u3068\u3092\u610F\u5473\u3057\u307E\u3059\u3002\u3053\u306E\u30D7\u30ED\
  \u30BB\u30B9\u306F\u3001\u5165\u529B\u30C7\u30FC\u30BF\u306E\u30B5\u30CB\u30BF\u30A4\
  \u30B8\u30F3\u30B0\u3001\u30D5\u30A1\u30A4\u30EB\u5185\u5BB9\u306E\u89E3\u6790\u3001\
  \u307E\u305F\u306F\u5F15\u7528\u7B26\u304C\u4E0D\u8981\u3067\u3042\u308B\u304B\u3001\
  \u30C7\u30FC\u30BF\u51E6\u7406\u3067\u30A8\u30E9\u30FC\u3092\u5F15\u304D\u8D77\u3053\
  \u3059\u53EF\u80FD\u6027\u304C\u3042\u308B\u5834\u9762\u3067\u6587\u5B57\u5217\u3092\
  \u3055\u3089\u306B\u51E6\u7406\u3059\u308B\u6E96\u5099\u3092\u3059\u308B\u305F\u3081\
  \u306B\u4E0D\u53EF\u6B20\u3067\u3059\u3002."
title: "\u6587\u5B57\u5217\u304B\u3089\u5F15\u7528\u7B26\u3092\u524A\u9664\u3059\u308B"
weight: 9
---

## 方法:
C言語で文字列から引用符を削除するには、引用符以外の文字だけを新しい文字列にコピーしながら文字列を走査します。このプロセスは、文字列に存在する引用符すべてを削除するか、あるいは先頭と末尾の引用符だけを削除するかに合わせて調整することができます。以下に示す例は、これらのアプローチの両方を示しています:

```c
#include <stdio.h>
#include <string.h>

// 文字列からすべての引用符を削除する関数
void removeAllQuotes(char *source, char *dest) {
    while (*source) {
        if (*source != '"' && *source != '\'') {
            *dest++ = *source;
        }
        source++;
    }
    *dest = '\0'; // 目的の文字列をヌル終端
}

// 文字列から先頭と末尾の引用符だけを削除する関数
void removeEdgeQuotes(char *source, char *dest) {
    size_t len = strlen(source);
    if (source[0] == '"' || source[0] == '\'') source++, len--;
    if (source[len-1] == '"' || source[len-1] == '\'') len--;
    strncpy(dest, source, len);
    dest[len] = '\0'; // 目的の文字列をヌル終端
}

int main() {
    char str1[] = "'Hello, World!'";
    char str2[] = "\"Programming in C\"";
    char noQuotes1[50];
    char noQuotes2[50];
    
    removeAllQuotes(str1, noQuotes1);
    printf("All Quotes Removed: %s\n", noQuotes1);
    
    removeEdgeQuotes(str2, noQuotes2);
    printf("Edge Quotes Removed: %s\n", noQuotes2);
    
    return 0;
}
```
サンプル出力:
```
All Quotes Removed: Hello, World!
Edge Quotes Removed: Programming in C
```

これらの例は、文字列に存在するすべての引用符の削除と、先頭と末尾の引用符だけの目標とした削除の両方をどのように扱うかを示しています。

## 深掘り
文字列から引用符を削除するという概念は、C言語において、初期のテキスト処理のニーズに結びついている以外に、顕著な歴史的深みがない。ここで示された直接的なアプローチは万能ですが、非常に大きい文字列や高性能を要求される場合、その場での修正やより高度なアルゴリズムが好まれる場合があり、効率性に欠けます。

`strpbrk`を使用して引用符を見つけ、引用符でない部分の文字列を移動するような代替方法はより効率的かもしれませんが、C言語でのポインターとメモリ管理についての深い理解を要求します。さらに、正規表現ライブラリの出現は、引用符の削除を含む文字列操作のための強力なツールセットを提供してきました。しかしながら、これらのライブラリは強力ですが、単純なタスクには必要のない複雑さとオーバーヘッドを加えるかもしれません。そのため、示された直接的なアプローチは、単純さと多くの一般的な用途での効果を組み合わせた、Cプログラマーにとって価値のあるスキルのままです。
