---
title:                "Поиск длины строки"
aliases:
- /ru/typescript/finding-the-length-of-a-string/
date:                  2024-01-28T23:58:30.252931-07:00
model:                 gpt-4-0125-preview
simple_title:         "Поиск длины строки"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/typescript/finding-the-length-of-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?

Нахождение длины строки означает измерение количества символов в ней. Программисты делают это для валидации ввода, перебора символов или ограничения отображаемого текста, среди прочего.

## Как это сделать:

В TypeScript длину строки можно узнать, используя свойство `.length`. Вот быстрый пример:

```typescript
let greeting: string = "Привет, TypeScript!";
console.log(greeting.length); // Вывод: 18
```

Этот код объявляет строковую переменную с именем `greeting` и затем выводит её длину в консоль.

## Глубокое погружение

Свойство `.length` унаследовано от JavaScript, предшественника TypeScript. Это простой и универсально поддерживаемый способ получения размера строки.

Существуют альтернативы, но они обычно усложняют задачу. Например, можно преобразовать строку в массив и подсчитать элементы:

```typescript
let greetingArray: string[] = Array.from(greeting);
console.log(greetingArray.length); // Вывод: 18
```

Но зачем идти длинным путем? Свойство `.length` эффективно, потому что строки хранятся в виде массивов символов под капотом, так что информация о длине немедленно доступна.

Теперь, допустим, вы работаете со строками на разных языках. Вы можете столкнуться с проблемами со специальными символами. Базовый подход с `.length` подсчитывает единицы кода UTF-16, что может быть проблематично для символов, требующих две единицы кода, известных как суррогатные пары. В таких случаях свойство `.length` может не дать вам подсчета фактических символов, также известных как кодовые точки.

Вот как вы можете обрабатывать строки с суррогатными парами:

```typescript
function countCodePoints(str: string): number {
    return Array.from(str).length;
}

let fancyGreeting: string = "Привет, 🌍!";
console.log(countCodePoints(fancyGreeting)); // Вывод: 9
```

Эта функция занимается тонкостями кодирования строк, чтобы обеспечить, чтобы каждый символ, независимо от того, состоит он из одной или двух единиц кода, был правильно подсчитан.

## Смотрите также

- Руководство по TypeScript о строках: [Руководство по TypeScript](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#strings)
- MDN Web Docs о свойстве длины строки: [String.prototype.length](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- Unicode и JavaScript: [У JavaScript есть проблема с Unicode - Матиас Биненс](https://mathiasbynens.be/notes/javascript-unicode)
