---
title:                "Использование интерактивной оболочки (REPL)"
aliases:
- /ru/typescript/using-an-interactive-shell-repl/
date:                  2024-01-29T00:04:34.386349-07:00
model:                 gpt-4-0125-preview
simple_title:         "Использование интерактивной оболочки (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/typescript/using-an-interactive-shell-repl.md"
changelog:
  - 2024-01-29, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и почему?
Read-Eval-Print-Loop (REPL) — это программная среда, которая принимает отдельные вводы пользователя, выполняет их и возвращает результат пользователю. Программисты используют REPL для быстрого экспериментирования с фрагментами кода, отладки и изучения новых возможностей языка без необходимости создания полноценного приложения.

## Как использовать:
TypeScript не поставляется со своим собственным REPL. Давайте используем `ts-node`, среду выполнения TypeScript для Node.js, которая включает REPL.

Сначала установите его глобально:
```bash
npm install -g ts-node
```

Запустите REPL, набрав `ts-node` в командной строке:
```bash
ts-node
```

Вот простой пример для тестирования:
```TypeScript
> let message: string = 'Привет, REPL!';
> console.log(message);
Привет, REPL!
> 
```
Чтобы завершить сессию, нажмите `Ctrl+D`.

## Подробнее
Исторически REPL были широко распространены в таких языках, как Lisp, позволяя динамически оценивать код. С тех пор концепция распространилась и стала основным элементом интерактивного программирования на многих языках.

Для TypeScript, `ts-node` — не единственный вариант. К альтернативам относятся использование TypeScript Playground в веб-браузере или использование других REPL, основанных на Node.js, которые поддерживают TypeScript с подходящими плагинами.

С точки зрения реализации, `ts-node` использует API компилятора TypeScript для транспиляции кода на лету перед его выполнением Node.js. Это дает вам немедленную обратную связь и особенно полезно для испытания последних функций TypeScript без проблем с настройкой.

Одно важное замечание — хотя REPL отлично подходит для быстрых тестов, он не заменяет написание традиционного, тестируемого и поддерживаемого кода. Это инструмент для обучения и исследования, а не замена надлежащим практикам разработки.

## См. также
- [Официальный сайт TypeScript](https://www.typescriptlang.org/)
- [ts-node на GitHub](https://github.com/TypeStrong/ts-node)
- [Документация REPL Node.js](https://nodejs.org/api/repl.html)
- [TypeScript Playground](https://www.typescriptlang.org/play)
