---
aliases:
- /ja/typescript/writing-to-standard-error/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:55.021319-07:00
description: "\u2026"
lastmod: 2024-02-18 23:08:54.697479
model: gpt-4-0125-preview
summary: "\u2026"
title: "\u6A19\u6E96\u30A8\u30E9\u30FC\u3078\u306E\u66F8\u304D\u8FBC\u307F"
---

{{< edit_this_page >}}

## 何となぜ？
TypeScriptでは、標準エラー（stderr）に書き込むことは、エラーメッセージやログを環境のエラー出力ストリーム（例えば、node.jsやWebブラウザのコンソール）に直接送信するプロセスです。これは、通常プログラムデータに使用される標準出力（stdout）と干渉せずに、問題の診断を確実に行うために不可欠です。これにより、エラー処理とロギングが効率的かつ一貫して管理されます。

## 方法：
TypeScriptはJavaScriptのスーパーセットであるため、stderrへの書き込みには基盤となるJSのランタイム環境（Node.jsなど）に依存しています。これが直接行う方法です：

```typescript
console.error("これはエラーメッセージです。");
```

stderrへのサンプル出力：
```
これはエラーメッセージです。
```

Node.js環境では、より低レベルの書き込みに`process.stderr.write()`メソッドも使用できます：

```typescript
process.stderr.write("低レベルのエラーメッセージ。\n");
```

stderrへのサンプル出力：
```
低レベルのエラーメッセージ。
```

より構造化されたエラーロギングには、`winston`や`pino`などの人気のサードパーティライブラリを使用することがあります。ここでは、`winston`を使ってエラーをログする方法を紹介します：

まず、`winston`をインストールします：

```bash
npm install winston
```

次に、TypeScriptファイルでそれを使用します：

```typescript
import * as winston from 'winston';

const logger = winston.createLogger({
  levels: winston.config.syslog.levels,
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'error.log', level: 'error' })
  ],
});

logger.error('winstonを使用してログされたエラー。');
```

これにより、エラーはコンソールと`error.log`という名前のファイルの両方に書き込まれます。ファイルに書き込む場合、ディスクスペースの使用に関連する問題を防ぐために、ファイルの権限とロールオーバーを管理することが重要です。
