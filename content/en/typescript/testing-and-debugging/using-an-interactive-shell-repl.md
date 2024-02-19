---
aliases:
- /en/typescript/using-an-interactive-shell-repl/
date: 2024-01-25 03:40:13.920163-07:00
description: "A Read-Eval-Print-Loop (REPL) is a programming environment that takes\
  \ single user inputs, executes them, and returns the result to the user. Programmers\u2026"
lastmod: 2024-02-18 23:09:10.808893
model: gpt-4-1106-preview
summary: "A Read-Eval-Print-Loop (REPL) is a programming environment that takes single\
  \ user inputs, executes them, and returns the result to the user. Programmers\u2026"
title: Using an interactive shell (REPL)
---

{{< edit_this_page >}}

## What & Why?
A Read-Eval-Print-Loop (REPL) is a programming environment that takes single user inputs, executes them, and returns the result to the user. Programmers use a REPL to quickly experiment with code snippets, debug, and learn new language features without the overhead of creating a full application.

## How to:
TypeScript doesn't come with its own REPL. Let's use `ts-node`, a TypeScript execution environment for Node.js that includes a REPL.

First, install it globally:
```bash
npm install -g ts-node
```

Start the REPL by typing `ts-node` in your command line:
```bash
ts-node
```

Here's a quick snippet to try:
```TypeScript
> let message: string = 'Hello, REPL!';
> console.log(message);
Hello, REPL!
> 
```
To end the session, press `Ctrl+D`.

## Deep Dive
Historically, REPLs were prominent in languages like Lisp, allowing for dynamic code evaluation. The concept has since spread, becoming a staple for interactive coding in many languages.

For TypeScript, `ts-node` isn't your only option. Alternatives include using the TypeScript Playground in a web browser or leveraging other Node.js-based REPLs that support TypeScript with suitable plugins.

In terms of implementation, `ts-node` uses the TypeScript compiler API to transpile code on-the-fly before it is executed by Node.js. This gives you immediate feedback and is particularly useful for trying out TypeScript's latest features without setup hassles.

One thing to remember – while a REPL is great for quick tests, it doesn't replace writing traditional, testable, and maintainable code. It's a tool for learning and exploration, not a substitute for proper development practices.

## See Also
- [TypeScript Official Website](https://www.typescriptlang.org/)
- [ts-node on GitHub](https://github.com/TypeStrong/ts-node)
- [Node.js REPL Documentation](https://nodejs.org/api/repl.html)
- [TypeScript Playground](https://www.typescriptlang.org/play)
