---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:58:27.350751-07:00
description: "C\u3067\u306E\u30A8\u30E9\u30FC\u51E6\u7406\u306F\u3001\u30D7\u30ED\u30B0\
  \u30E9\u30E0\u5B9F\u884C\u4E2D\u306B\u767A\u751F\u3059\u308B\u7570\u5E38\u306A\u72B6\
  \u6CC1\u3092\u691C\u51FA\u3057\u3066\u5BFE\u5FDC\u3059\u308B\u3053\u3068\u3092\u542B\
  \u307F\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\u308C\u3092\
  \u884C\u3046\u3053\u3068\u3067\u3001\u30D0\u30B0\u3001\u30AF\u30E9\u30C3\u30B7\u30E5\
  \u3001\u305D\u3057\u3066\u4E88\u6E2C\u4E0D\u53EF\u80FD\u306A\u632F\u308B\u821E\u3044\
  \u3092\u9632\u304E\u3001\u3055\u307E\u3056\u307E\u306A\u30B7\u30CA\u30EA\u30AA\u306E\
  \u4E0B\u3067\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\u304C\u4FE1\u983C\u6027\u3068\u52B9\
  \u7387\u7684\u306B\u6A5F\u80FD\u3059\u308B\u3053\u3068\u3092\u4FDD\u8A3C\u3057\u307E\
  \u3059\u3002"
lastmod: '2024-03-13T22:44:42.808039-06:00'
model: gpt-4-0125-preview
summary: "C\u3067\u306E\u30A8\u30E9\u30FC\u51E6\u7406\u306F\u3001\u30D7\u30ED\u30B0\
  \u30E9\u30E0\u5B9F\u884C\u4E2D\u306B\u767A\u751F\u3059\u308B\u7570\u5E38\u306A\u72B6\
  \u6CC1\u3092\u691C\u51FA\u3057\u3066\u5BFE\u5FDC\u3059\u308B\u3053\u3068\u3092\u542B\
  \u307F\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\u308C\u3092\
  \u884C\u3046\u3053\u3068\u3067\u3001\u30D0\u30B0\u3001\u30AF\u30E9\u30C3\u30B7\u30E5\
  \u3001\u305D\u3057\u3066\u4E88\u6E2C\u4E0D\u53EF\u80FD\u306A\u632F\u308B\u821E\u3044\
  \u3092\u9632\u304E\u3001\u3055\u307E\u3056\u307E\u306A\u30B7\u30CA\u30EA\u30AA\u306E\
  \u4E0B\u3067\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\u304C\u4FE1\u983C\u6027\u3068\u52B9\
  \u7387\u7684\u306B\u6A5F\u80FD\u3059\u308B\u3053\u3068\u3092\u4FDD\u8A3C\u3057\u307E\
  \u3059\u3002."
title: "\u30A8\u30E9\u30FC\u51E6\u7406"
weight: 16
---

## 方法：
Cは他の言語のように例外のための組み込みサポートを持っていません。代わりに、関数から特別な値を返す、`errno`のようなグローバル変数を設定するなど、いくつかの従来のエラー処理戦略に頼っています。

**特別な値を返す**

関数は、有効な結果としてありそうにない特定の値を返すことでエラーを示すことができます。以下は整数の例です：

```c
#include <stdio.h>

int inverse(int number, double *result) {
    if (number == 0) {
        return -1; // エラーケース
    } else {
        *result = 1.0 / number;
        return 0; // 成功
    }
}

int main() {
    double result;
    if (inverse(0, &result) < 0) {
        printf("Error: Division by zero.\n");
    } else {
        printf("The inverse is: %f\n", result);
    }
    
    return 0;
}
```

**出力：**
```
Error: Division by zero.
```

**`errno`をチェックする**

システムやOS（ファイルI/Oなど）とやり取りする特にライブラリ関数では、エラーが発生すると`errno`が設定されます。これを使用するには、`errno.h`をインクルードして、予想される失敗の後で`errno`をチェックします：

```c
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main() {
    FILE *file = fopen("nonexistent.txt", "r");
    if (file == NULL) {
        printf("Error opening file: %s\n", strerror(errno));
    }
    
    return 0;
}
```

**出力：**
```
Error opening file: No such file or directory
```

## ディープダイブ
歴史的に、Cプログラミング言語のミニマリスティックなデザインは、その低レベルでシステムプログラミングの起源を反映し、最大の性能とメタルに近い制御が重要な場合に、組み込みの例外処理メカニズムを除外してきました。代わりに、Cはプログラマーに可能な限り多くの制御を提供するというその哲学に適合する、より手動のエラー処理アプローチを採用しています。これは便利さのコストであってもです。

このアプローチはCの設計目標とよく一致しているものの、冗長なエラーチェックコードや見逃されたエラーチェックの可能性を生じさせ、近代的な言語が構造化された例外処理メカニズムで対処しているものです。例えば、JavaやC#のような言語での例外は、エラー処理を中央化し、コードをクリーナーにし、エラー管理をより直接的にすることができます。しかし、例外はそれ自体のオーバーヘッドや複雑さを導入し、Cが輝くシステムレベルのプログラミングには理想的ではないかもしれません。

その粗野さにもかかわらず、Cにおけるこの手動のエラー処理は、エラー条件の明確さがより予測可能でデバッグしやすいコードにつながるモデルを多くの他の言語のエラー管理の設計に情報を提供しています。致命的なシステムで、障害を優雅に管理する必要がある場合、Cのエラー処理パラダイムは、エラー処理ライブラリや規約などの現代のベストプラクティスと組み合わせることで、堅牢性と信頼性を保証します。
