---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:54:15.751761-07:00
description: "C\u3067\u65E5\u4ED8\u3092\u6587\u5B57\u5217\u306B\u5909\u63DB\u3059\u308B\
  \u3053\u3068\u306F\u3001\u65E5\u4ED8\u69CB\u9020\u307E\u305F\u306F\u30BF\u30A4\u30E0\
  \u30B9\u30BF\u30F3\u30D7\u3092\u4EBA\u304C\u8AAD\u307F\u53D6\u308C\u308B\u5F62\u5F0F\
  \u306B\u7FFB\u8A33\u3059\u308B\u3053\u3068\u3092\u542B\u307F\u307E\u3059\u3002\u30D7\
  \u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30ED\u30B0\u3001\u30E6\u30FC\u30B6\u30FC\
  \u30A4\u30F3\u30BF\u30FC\u30D5\u30A7\u30FC\u30B9\u306B\u65E5\u4ED8\u3092\u8868\u793A\
  \u3057\u305F\u308A\u3001JSON\u3084CSV\u306E\u3088\u3046\u306A\u30C6\u30AD\u30B9\u30C8\
  \u30D9\u30FC\u30B9\u306E\u5F62\u5F0F\u3067\u65E5\u4ED8\u3092\u4FDD\u5B58\u3059\u308B\
  \u5834\u5408\u306B\u3001\u3057\u3070\u3057\u3070\u3053\u306E\u4F5C\u696D\u3092\u5B9F\
  \u884C\u3057\u307E\u3059\u3002"
lastmod: '2024-03-13T22:44:42.812917-06:00'
model: gpt-4-0125-preview
summary: "C\u3067\u65E5\u4ED8\u3092\u6587\u5B57\u5217\u306B\u5909\u63DB\u3059\u308B\
  \u3053\u3068\u306F\u3001\u65E5\u4ED8\u69CB\u9020\u307E\u305F\u306F\u30BF\u30A4\u30E0\
  \u30B9\u30BF\u30F3\u30D7\u3092\u4EBA\u304C\u8AAD\u307F\u53D6\u308C\u308B\u5F62\u5F0F\
  \u306B\u7FFB\u8A33\u3059\u308B\u3053\u3068\u3092\u542B\u307F\u307E\u3059\u3002\u30D7\
  \u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3001\u30ED\u30B0\u3001\u30E6\u30FC\u30B6\u30FC\
  \u30A4\u30F3\u30BF\u30FC\u30D5\u30A7\u30FC\u30B9\u306B\u65E5\u4ED8\u3092\u8868\u793A\
  \u3057\u305F\u308A\u3001JSON\u3084CSV\u306E\u3088\u3046\u306A\u30C6\u30AD\u30B9\u30C8\
  \u30D9\u30FC\u30B9\u306E\u5F62\u5F0F\u3067\u65E5\u4ED8\u3092\u4FDD\u5B58\u3059\u308B\
  \u5834\u5408\u306B\u3001\u3057\u3070\u3057\u3070\u3053\u306E\u4F5C\u696D\u3092\u5B9F\
  \u884C\u3057\u307E\u3059\u3002."
title: "\u65E5\u4ED8\u3092\u6587\u5B57\u5217\u306B\u5909\u63DB\u3059\u308B"
weight: 28
---

## 方法:
この目的のために一般的に使用されるのは、`<time.h>`ライブラリからの`strftime`関数です。これにより、形式指定子を指定することで、さまざまな方法で日付と時刻を形式化できます。こちらが簡単な例です:

```c
#include <stdio.h>
#include <time.h>

int main() {
    char dateStr[100];
    time_t now = time(NULL);
    struct tm *ptm = localtime(&now);

    // 日付と時刻を文字列に変換（例: "Wed Jun 30 21:49:08 2021"）
    strftime(dateStr, sizeof(dateStr), "%a %b %d %H:%M:%S %Y", ptm);
    
    printf("現在の日付と時刻: %s\n", dateStr);
    return 0;
}
```

サンプル出力は次のようになるかもしれません:

```
現在の日付と時刻: Wed Jun 30 21:49:08 2021
```

`strftime`に渡される形式指定子を変更することで、形式をカスタマイズできます。例えば、日付を`YYYY-MM-DD`の形式で取得するには、`"%Y-%m-%d"`を使用します。

## 深掘り
`strftime`関数と`<time.h>`ライブラリは、C標準ライブラリの一部であり、元々のANSI C標準（C89/C90）にさかのぼります。このアプローチは多くのプラットフォームでサポートされており、直接的であるものの、より直感的な日付と時刻のライブラリを備えた現代のプログラミング言語と比べると、低レベルで面倒に見えるかもしれません。

C標準ライブラリの時間関数は広くサポートされており比較的簡単に使用できるものの、新しい言語のライブラリや国際化機能を備えたサードパーティCライブラリ（例：International Components for Unicode (ICU)）に見られるような複雑なタイムゾーン操作や国際化機能には欠けています。

それでも、`strftime`関数のカスタマイズ能力と広範なプラットフォームサポートは、Cでの日付文字列変換において信頼でき、有益なツールであることを意味します。より高レベルのdatetimeライブラリから来たプログラマーは、その低レベルな性質に慣れる必要があるかもしれませんが、多様なアプリケーションでの日付と時刻のフォーマットに際して、それが非常に強力で多様性があることを見いだすでしょう。
