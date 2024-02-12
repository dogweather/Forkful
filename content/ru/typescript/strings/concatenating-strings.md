---
title:                "Склеивание строк"
aliases:
- ru/typescript/concatenating-strings.md
date:                  2024-01-28T23:56:50.731215-07:00
model:                 gpt-4-0125-preview
simple_title:         "Склеивание строк"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/typescript/concatenating-strings.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?

Конкатенация строк - это склеивание двух или более строк в одну. Программисты делают это для формирования сообщений, создания динамического контента или для любых других нужд, требующих гибкого соединения текста.

## Как это сделать:

```TypeScript
let greeting: string = "Привет";
let target: string = "Мир";
let message: string = greeting + ", " + target + "!"; // используя оператор +
console.log(message); // Вывод: Привет, Мир!

let anotherMessage: string = `${greeting}, ${target}!`; // используя шаблонные литералы
console.log(anotherMessage); // Вывод: Привет, Мир!
```

## Подробнее

Конкатенация - это основа; она существует с первых дней программирования. В TypeScript, который построен на основе JavaScript, мы проделали долгий путь от громоздких операций со строками до изящных шаблонных литералов.

Исторически приходилось быть осторожным с конкатенацией, чтобы не использовать слишком много памяти или не замедлить браузер. Современные движки оптимизированы, но эффективность по-прежнему важна в масштабных приложениях.

Есть альтернативы:
1. Массивы и `.join()`: Полезны, когда вы работаете со списком строк.
2. Паттерны StringBuilder: Более актуальны для языков, таких как Java или C#, где это оптимизирует производительность.

С точки зрения реализации, TypeScript в конечном итоге компилируется в JavaScript. Под капотом он использует те же функции и операции со строками, что и JavaScript.

## Смотрите также

- Вам может быть интересно ознакомиться с документацией Mozilla Developer Network по работе со строками [Документация по строкам](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/String) для более глубокого изучения методов работы со строками.
- Для вопросов, специфичных для TypeScript, [официальная документация TypeScript](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#string) представляет собой краткий справочник.
