---
aliases:
- /ja/c/converting-a-string-to-lower-case/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:54:46.569303-07:00
description: "C\u8A00\u8A9E\u3067\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\
  \u63DB\u3059\u308B\u3053\u3068\u306F\u3001\u4E0E\u3048\u3089\u308C\u305F\u6587\u5B57\
  \u5217\u306E\u3059\u3079\u3066\u306E\u5927\u6587\u5B57\u3092\u305D\u308C\u306B\u5BFE\
  \u5FDC\u3059\u308B\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\u4F5C\u696D\u3092\
  \u542B\u307F\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\u306E\
  \u64CD\u4F5C\u3092\u3001\u6BD4\u8F03\u3001\u691C\u7D22\u64CD\u4F5C\u306E\u305F\u3081\
  \u306E\u30C6\u30AD\u30B9\u30C8\u5165\u529B\u306E\u6A19\u6E96\u5316\u3001\u307E\u305F\
  \u306F\u5358\u306B\u51FA\u529B\u306E\u898B\u305F\u76EE\u306E\u4E00\u8CAB\u6027\u306E\
  \u305F\u3081\u306B\u3088\u304F\u884C\u3044\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:55.336706
model: gpt-4-0125-preview
summary: "C\u8A00\u8A9E\u3067\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\
  \u63DB\u3059\u308B\u3053\u3068\u306F\u3001\u4E0E\u3048\u3089\u308C\u305F\u6587\u5B57\
  \u5217\u306E\u3059\u3079\u3066\u306E\u5927\u6587\u5B57\u3092\u305D\u308C\u306B\u5BFE\
  \u5FDC\u3059\u308B\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\u4F5C\u696D\u3092\
  \u542B\u307F\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\u306E\
  \u64CD\u4F5C\u3092\u3001\u6BD4\u8F03\u3001\u691C\u7D22\u64CD\u4F5C\u306E\u305F\u3081\
  \u306E\u30C6\u30AD\u30B9\u30C8\u5165\u529B\u306E\u6A19\u6E96\u5316\u3001\u307E\u305F\
  \u306F\u5358\u306B\u51FA\u529B\u306E\u898B\u305F\u76EE\u306E\u4E00\u8CAB\u6027\u306E\
  \u305F\u3081\u306B\u3088\u304F\u884C\u3044\u307E\u3059\u3002"
title: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B"
---

{{< edit_this_page >}}

## なぜ & どうやって?

C言語で文字列を小文字に変換することは、与えられた文字列のすべての大文字をそれに対応する小文字に変換する作業を含みます。プログラマーはこの操作を、比較、検索操作のためのテキスト入力の標準化、または単に出力の見た目の一貫性のためによく行います。

## 方法:

Cには、高レベル言語のような文字列を直接小文字に変換する組み込みの関数はありません。しかし、C標準ライブラリ関数を使用して、このプロセスを簡単に実装することができます。以下に、文字列を小文字に変換する方法とその例をステップバイステップで説明します。

```c
#include <stdio.h>
#include <ctype.h>

void toLowerCase(char *str) {
    while (*str) {
        *str = tolower(*str);
        str++;
    }
}

int main() {
    char text[] = "Hello, World!";
    printf("Original: %s\n", text);

    toLowerCase(text);
    printf("Lowercase: %s\n", text);

    return 0;
}
```

**サンプル出力:**

```
Original: Hello, World!
Lowercase: hello, world!
```

この例では、`toLowerCase`関数は入力文字列の各文字をイテレートし、`ctype.h`の`tolower`関数を使用して、それを小文字の等価物に変換します。修正は元の文字列を変更する形で行われます。

## 詳細解説

上記の例で使用される`tolower`関数は、C標準ライブラリの一部であり、具体的には`ctype.h`ヘッダーファイル内にあります。これは現在のロケールに基づいて動作しますが、標準の"C"ロケールの場合、ASCII文字セットにおいて'A'から'Z'は'a'から'z'に変換されます。

歴史的に、Cでの文字エンコーディングとケース変換の処理はASCII文字セットと密接に結びついており、ASCIIセット外の文字が一般的な国際的またはローカライズされたアプリケーションではその有用性に限界がありました。現代のプログラミング言語では、ロケールとUnicode文字を考慮してケース変換を行う組み込みの文字列メソッドを提供するかもしれませんが、Cにはネイティブにはそれがありません。

ASCII文字以外のテキスト操作、特に非ASCII文字を多用するシナリオでは、ICU（International Components for Unicode）など、より良い国際化サポートを提供するライブラリの使用を検討するかもしれません。しかし、ASCIIテキストを扱うほとんどのアプリケーションにとって、示されたアプローチは効率的で直接的です。これは、高レベル言語と比較してもう少し手間がかかるとしても、プログラマーがデータ操作をコントロールするCの傾向を示しています。
