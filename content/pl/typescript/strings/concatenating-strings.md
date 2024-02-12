---
title:                "Łączenie łańcuchów znaków"
date:                  2024-01-20T17:35:40.731035-07:00
model:                 gpt-4-1106-preview
simple_title:         "Łączenie łańcuchów znaków"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/typescript/concatenating-strings.md"
---

{{< edit_this_page >}}

## What & Why? (Co i dlaczego?)
Łączymy napisy (stringi), żeby uformować nowy, większy tekst. Robimy to, by wyświetlić komunikaty, zbudować zapytania do bazy danych, albo po prostu skleić różne kawałki informacji w całość.

## How to: (Jak to zrobić:)
```TypeScript
let greeting: string = "Cześć";
let who: string = "świecie";
let exclamation: string = "!";

// Klasyczny sposób za pomocą operatora '+':
let classicConcatenation = greeting + ", " + who + exclamation;
console.log(classicConcatenation);  // "Cześć, świecie!"

// Template strings (od ES6 czyli TypeScript również):
let templateConcatenation = `${greeting}, ${who}${exclamation}`;
console.log(templateConcatenation);  // "Cześć, świecie!"
```

## Deep Dive (Dogłębna analiza)
Historically, JavaScript developers used the '+' operator for string concatenation. With the introduction of ES6 (a significant update to JavaScript upon which TypeScript is built), template literals—delimited by backticks (`) instead of quotes—came into play, allowing for multiline strings and string interpolation (embedded expressions).

Alternatives to '+' include `concat()` method and array’s `join()` method, though these are less common in modern code:

```TypeScript
// concat() metoda:
let concatMethod = greeting.concat(", ", who, exclamation);
console.log(concatMethod);  // Cześć, świecie!

// join() metoda z użyciem tablicy:
let arrayJoin = [greeting, who].join(", ") + exclamation;
console.log(arrayJoin);  // Cześć, świecie!
```

Under the hood, when you use '+', JavaScript engines can optimize string concatenation efficiently, especially for short and simple operations. However, for complex or large-scale string-building tasks, template literals may offer better performance and readability.

## See Also (Zobacz również)
- [MDN Web Docs on Template Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
