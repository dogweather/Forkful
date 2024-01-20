---
title:                "Знаходження довжини рядка"
html_title:           "Arduino: Знаходження довжини рядка"
simple_title:         "Знаходження довжини рядка"
programming_language: "Javascript"
category:             "Javascript"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/javascript/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## Що і Навіщо?

Знаходження довжини рядка - це процес визначення кількості символів у текстовому рядку. Програмісти це роблять для обробки тексту, керування пам'яттю та запобігання помилкам.

## Як це робити:

У JavaScript ви можете використовувати властивість `length` для отримання довжини рядка. Ось як це працює:

```Javascript
let text = 'JavaScript! Українською';
console.log(text.length);  // Виведе: 24
```

У вищенаведеному коді `length` повертає довжину рядка, в цьому випадку 24 символи.

## Поглиблений огляд:

Історично в JavaScript рядки представляє універсальний набір символів Unicode. Вони завжди кодуються в UTF-16, що робить `length` ефективним інструментом.

Варто пам'ятати, що `length` не завжди повертає очікувану кількість "символів". При роботі з емодзі або іншими символами багатобайтового кодування, може статися, що `length` поверне більший результат.

У якості альтернативи, можна використовувати набори символів та ітератори, ітерувати через рядок символ за символом:

```Javascript
[...'🙂🙃'].length  // Виведе: 2
```

Вищезазначений код вірно обробляє багатобайтові символи.

## Дивіться також:

1.  [MDN рядки та робота з рядками в JavaScript](https://developer.mozilla.org/uk/docs/Web/JavaScript/Guide/Text_formatting)
2.  [Робота з Unicode в JavaScript](https://mathiasbynens.be/notes/javascript-unicode)
3.  [ECMAScript® 2021 мовні специфікації](https://tc39.es/ecma262/#sec-string-length)