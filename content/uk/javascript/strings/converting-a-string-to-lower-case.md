---
date: 2024-01-20 17:38:42.077426-07:00
description: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F\
  \ \u0440\u044F\u0434\u043A\u0430 \u0432 \u043D\u0438\u0436\u043D\u0456\u0439 \u0440\
  \u0435\u0433\u0456\u0441\u0442\u0440 \u043E\u0437\u043D\u0430\u0447\u0430\u0454\
  \ \u0437\u0430\u043C\u0456\u043D\u0443 \u0432\u0441\u0456\u0445 \u0432\u0435\u043B\
  \u0438\u043A\u0438\u0445 \u043B\u0456\u0442\u0435\u0440 \u043D\u0430 \u043C\u0430\
  \u043B\u0435\u043D\u044C\u043A\u0456. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\
  \u0456\u0441\u0442\u0438 \u0446\u0435 \u0440\u043E\u0431\u043B\u044F\u0442\u044C\
  \ \u0434\u043B\u044F \u0443\u043D\u0456\u0444\u0456\u043A\u0430\u0446\u0456\u0457\
  \ \u0434\u0430\u043D\u0438\u0445, \u0441\u043F\u0440\u043E\u0449\u0435\u043D\u043D\
  \u044F \u043F\u043E\u0440\u0456\u0432\u043D\u044F\u043D\u043D\u044F\u2026"
lastmod: '2024-03-13T22:44:49.970379-06:00'
model: gpt-4-1106-preview
summary: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F\
  \ \u0440\u044F\u0434\u043A\u0430 \u0432 \u043D\u0438\u0436\u043D\u0456\u0439 \u0440\
  \u0435\u0433\u0456\u0441\u0442\u0440 \u043E\u0437\u043D\u0430\u0447\u0430\u0454\
  \ \u0437\u0430\u043C\u0456\u043D\u0443 \u0432\u0441\u0456\u0445 \u0432\u0435\u043B\
  \u0438\u043A\u0438\u0445 \u043B\u0456\u0442\u0435\u0440 \u043D\u0430 \u043C\u0430\
  \u043B\u0435\u043D\u044C\u043A\u0456."
title: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F \u0440\
  \u044F\u0434\u043A\u0430 \u0443 \u043D\u0438\u0436\u043D\u0456\u0439 \u0440\u0435\
  \u0433\u0456\u0441\u0442\u0440"
weight: 4
---

## Як це зробити:
```javascript
let phrase = "Привіт, Світе!";
let lowerCasePhrase = phrase.toLowerCase();
console.log(lowerCasePhrase); // Output: "привіт, світе!"
```

```javascript
let greeting = "ЗдОрОвЕнЬкІ БулИ!";
console.log(greeting.toLowerCase()); // Output: "здоровенькі були!"
```

## Підводне каміння:
Історично, метод `toLowerCase` був частиною Javascript з його перших версій. Він відноситься до прототипу String і тому доступний для всіх рядків. Є альтернативи, наприклад `toLocaleLowerCase()`, яка враховує локалізацію, тобто певні мовні особливості при переведенні у нижній регістр.

Реалізація `toLowerCase` у браузерах та серверних середовищах, як Node.js, гарантує, що вона працюватиме однаково універсально. Однак, слід звернути увагу на специфічні символи та літери, які можуть мати особливі правила перетворення в окремих мовах. Для більшості випадків `toLowerCase` повинен працювати без зайвих проблем.

## Дивіться також:
- Документація MDN за методом `toLowerCase()`: [Mozilla MDN toLowerCase](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
- Порівняння `toLowerCase()` та `toLocaleLowerCase()`: [toLocaleLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleLowerCase)
- Рекомендації по стилі коду з Airbnb, де згадується використання методів рядків: [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
