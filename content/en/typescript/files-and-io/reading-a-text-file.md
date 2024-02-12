---
title:                "Reading a text file"
date:                  2024-01-20T17:55:05.959383-07:00
model:                 gpt-4-1106-preview
simple_title:         "Reading a text file"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/typescript/reading-a-text-file.md"
---

{{< edit_this_page >}}

## What & Why?

Reading a text file is grabbing the content from a file that's structured as human-readable text. Programmers do it to process or analyze the data, like reading configuration, importing data, or simply ingesting content to be processed by an application.

## How to:

Let's read a text file in TypeScript using Node.js's `fs/promises` module. We'll keep this example simple: read a file named `example.txt` and log its content.

```typescript
import { readFile } from 'fs/promises';

async function readTextFile(filePath: string) {
  try {
    const data = await readFile(filePath, 'utf8');
    console.log(data);
  } catch (error) {
    console.error(`Error reading file from disk: ${error}`);
  }
}

readTextFile('./example.txt');
```

Sample Output:
```
Hello, this is content from the file!
```

## Deep Dive

Historically, file reading in Node.js was heavily callback-based, which could lead to a phenomenon known as "callback hell". With the advent of Promises and `async/await`, this process became much more streamlined.

Besides `fs/promises`, there's the older `fs` module that still works with callback patterns. There's also the option of using stream processing with `fs.createReadStream()`, useful for large files due to lower memory consumption.

Implementation-wise, accessing the file system is an I/O operation and inherently slower than in-memory operations. That's why asynchronous coding patterns are important — they help prevent blocking the main thread and allow Node.js to keep handling other tasks.

## See Also

For a deeper dive into Node.js file system:
- Node.js fs documentation: https://nodejs.org/api/fs.html
- Understanding `fs/promises`: https://nodejs.org/dist/latest/docs/api/fs.html#filehandlepromises
- Stream-based file reading: https://nodejs.org/api/stream.html#stream
For TypeScript specific resources:
- TypeScript Deep Dive: https://basarat.gitbook.io/typescript/
- TypeScript Handbook: https://www.typescriptlang.org/docs/handbook/intro.html
