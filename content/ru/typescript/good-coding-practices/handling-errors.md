---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:59:16.445777-07:00
description: "\u041E\u0431\u0440\u0430\u0431\u043E\u0442\u043A\u0430 \u043E\u0448\u0438\
  \u0431\u043E\u043A \u0437\u0430\u043A\u043B\u044E\u0447\u0430\u0435\u0442\u0441\u044F\
  \ \u0432 \u043E\u0436\u0438\u0434\u0430\u043D\u0438\u0438 \u043D\u0435\u043E\u0436\
  \u0438\u0434\u0430\u043D\u043D\u043E\u0433\u043E; \u044D\u0442\u043E \u0442\u043E\
  , \u043A\u0430\u043A \u043C\u044B \u0441\u043F\u0440\u0430\u0432\u043B\u044F\u0435\
  \u043C\u0441\u044F, \u043A\u043E\u0433\u0434\u0430 \u0432 \u043D\u0430\u0448\u0435\
  \u043C \u043A\u043E\u0434\u0435 \u0447\u0442\u043E-\u0442\u043E \u0438\u0434\u0435\
  \u0442 \u043D\u0435 \u0442\u0430\u043A. \u041C\u044B \u0434\u0435\u043B\u0430\u0435\
  \u043C \u044D\u0442\u043E, \u0447\u0442\u043E\u0431\u044B \u0438\u0437\u0431\u0435\
  \u0436\u0430\u0442\u044C\u2026"
lastmod: '2024-03-13T22:44:44.602793-06:00'
model: gpt-4-0125-preview
summary: "\u041E\u0431\u0440\u0430\u0431\u043E\u0442\u043A\u0430 \u043E\u0448\u0438\
  \u0431\u043E\u043A \u0437\u0430\u043A\u043B\u044E\u0447\u0430\u0435\u0442\u0441\u044F\
  \ \u0432 \u043E\u0436\u0438\u0434\u0430\u043D\u0438\u0438 \u043D\u0435\u043E\u0436\
  \u0438\u0434\u0430\u043D\u043D\u043E\u0433\u043E; \u044D\u0442\u043E \u0442\u043E\
  , \u043A\u0430\u043A \u043C\u044B \u0441\u043F\u0440\u0430\u0432\u043B\u044F\u0435\
  \u043C\u0441\u044F, \u043A\u043E\u0433\u0434\u0430 \u0432 \u043D\u0430\u0448\u0435\
  \u043C \u043A\u043E\u0434\u0435 \u0447\u0442\u043E-\u0442\u043E \u0438\u0434\u0435\
  \u0442 \u043D\u0435 \u0442\u0430\u043A."
title: "\u041E\u0431\u0440\u0430\u0431\u043E\u0442\u043A\u0430 \u043E\u0448\u0438\u0431\
  \u043E\u043A"
weight: 16
---

## Как:
В TypeScript обработка ошибок часто включает блоки `try`, `catch` и `finally`.

```typescript
function riskyOperation() {
  throw new Error("Что-то пошло не так!");
}

function handleErrors() {
  try {
    riskyOperation();
  } catch (error) {
    console.error("Ошибка перехвачена:", error.message);
  } finally {
    console.log("Это выполняется всегда, была ошибка или нет.");
  }
}

handleErrors();
```

Пример вывода:

```
Ошибка перехвачена: Что-то пошло не так!
Это выполняется всегда, была ошибка или нет.
```

Асинхронный пример с промисами:

```typescript
async function asyncRiskyOperation() {
  return new Promise((resolve, reject) => {
    // Имитация ошибки
    reject("Катастрофическая неудача");
  });
}

async function handleAsyncErrors() {
  try {
    await asyncRiskyOperation();
  } catch (error) {
    console.error("Асинхронная ошибка перехвачена:", error);
  }
}

handleAsyncErrors();
```

Пример вывода:

```
Асинхронная ошибка перехвачена: Катастрофическая неудача
```

## Глубже в Тему
Обработка ошибок является краеугольным камнем программирования с момента его зарождения. В TypeScript, который построен на основе JavaScript, обработка ошибок стала более надежной с введением async/await в ECMAScript 2017. До этого мы часто полагались на функции обратного вызова и промисы для обработки ошибок в асинхронном коде.

Альтернативой `try/catch` в TypeScript является использование границ ошибок, предоставляемых фреймворками, такими как React. Для серверной обработки мы можем использовать промежуточное ПО на платформах вроде Express.js для централизации управления ошибками.

С точки зрения реализации, TypeScript не имеет собственного механизма обработки ошибок, но опирается на механизм JavaScript. Пользовательские классы ошибок могут наследовать класс `Error`, чтобы предоставлять более описательную информацию об ошибках.

## Смотрите Также
- [MDN о try/catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch)
- [Async/Await на MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)
- [Использование границ ошибок в React](https://reactjs.org/docs/error-boundaries.html)
- [Обработка ошибок в Express.js](https://expressjs.com/en/guide/error-handling.html)
