---
title:                "Визначення довжини рядка"
aliases:
- uk/typescript/finding-the-length-of-a-string.md
date:                  2024-01-20T17:48:34.564337-07:00
model:                 gpt-4-1106-preview
simple_title:         "Визначення довжини рядка"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/typescript/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## Що та Чому?
Знаходження довжини рядка - це процес отримання кількості символів у ньому. Програмісти використовують це для валідації, обробки даних та управління текстовими форматами.

## Як це зробити:
Для отримання довжини рядка в TypeScript, використовуйте властивість `length`.

```typescript
let message: string = "Вітаю";
console.log(message.length); // Виводить: 6
```

Якщо рядок порожній, `length` поверне 0.

```typescript
let emptyMessage: string = "";
console.log(emptyMessage.length); // Виводить: 0
```

## Поглиблено:
Довжина рядка широко використовується із часів створення перших мов програмування. У JavaScript та TypeScript, `length` є властивістю прототипу `String`, і вона моментально повертає кількість UTF-16 кодових одиниць у рядку, що не завжди співпадає з кількістю видимих символів у рядку з емоджі або іншими особливими символами.

Як альтернатива, для отримання довжини, що враховує Unicode, можна використовувати `Array.from()` або spread оператор:

```typescript
let emojiMessage: string = "Привіт 👋";
console.log(Array.from(emojiMessage).length); // Виводить: 8
```

Але зауважте, це може бути повільніше ніж просте використання `length`.

## Дивіться також:
- MDN документація про String.length: [MDN String.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- Стаття про роботу з Unicode у JavaScript: [Handling Unicode](https://flaviocopes.com/javascript-unicode/)
- Типізація рядків у TypeScript: [TypeScript String](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)
