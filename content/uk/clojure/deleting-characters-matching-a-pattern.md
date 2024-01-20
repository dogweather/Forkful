---
title:                "Видалення символів, що відповідають патерну"
html_title:           "Arduino: Видалення символів, що відповідають патерну"
simple_title:         "Видалення символів, що відповідають патерну"
programming_language: "Clojure"
category:             "Clojure"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/clojure/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## Що та навіщо?
Видалення символів за патерном - це процес, при якому програма видаляє символи з рядка, що відповідають певному шаблону. Програмісти це роблять для очищення даних, видалення небажаних символів чи регулювання вводу користувачів.

## Як це зробити:
Ось приклад, як це можна зробити в Clojure:

```Clojure
(defn delete-pattern [s pattern]
  (clojure.string/replace s pattern ""))
```

Якщо ви хочете видалити всі числа з рядку, ви можете використовувати цей шаблон:

```Clojure
(delete-pattern "Я люблю Clojure 3000" #"\d+") 
```

Вихід:

```Clojure
"Я люблю Clojure "
```

## Поглиблений розгляд:
Видалення символів за партеном виходить із початкових концепцій обробки рядків в комп'ютерніх науках. Багато мов програмування, включаючи Java, Python, і JavaScript, мають вбудовані функції для цього завдання. В Clojure ми використовуємо регулярні вирази, щоб визначити патерн, та функцію `clojure.string/replace`, щоб видалити символи, які співпадають з цим патерном.

Існують альтернативи для цього завдання, такі як написання власних функцій, що ітерують крізь рядок та видаляють співпадаючі символи, але використання `clojure.string/replace` є найефективнішим та найчистішим способом.

## Додаткові матеріали:
Для того щоб дізнатися більше про обробку рядків в Clojure, відвідайте ці посилання:

1. [Clojure - String Functions](https://www.tutorialspoint.com/clojure/clojure_string_functions.htm)
2. [Clojure - Regular Expressions](https://www.tutorialspoint.com/clojure/clojure_regular_expressions.htm)

Також підкреслюється важливість розуміння регулярних виразів для обробки рядків. Для цього сильно раджу вам:

1. [Learn Regex the Easy Way](https://github.com/zeeshanu/learn-regex)
2. [Regexr](https://regexr.com/) – інтерактивний інструмент для навчання та перевірки регулярних виразів.