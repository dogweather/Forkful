---
title:                "Використання регулярних виразів"
html_title:           "Arduino: Використання регулярних виразів"
simple_title:         "Використання регулярних виразів"
programming_language: "Bash"
category:             "Bash"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/bash/using-regular-expressions.md"
---

{{< edit_this_page >}}

## Що це та навіщо?

Регулярні вирази - це могутній інструмент нотації для шаблонів тексту. Їх використовують програмісти для аналізу, перевірки, зміни або розбивки комплексних текстових даних.

## Як це робити:

Ось базовий приклад, як можна використовувати Bash для пошуку тексту за допомогою регулярних виразів:

```Bash 
echo 'Hello Dev!' | grep -o 'He.*'
```

Це виведе "Hello Dev", оскільки 'He.*' зазначає будь-який текст, що починається на "He" та закінчується будь-якими символами.

## Більш глибоке занурення:

Регулярні вирази були розроблені ще в 1951 році й стали ключовим інструментом в текстових програмах Unix. 

Хоча Bash об'єднує регулярні вирази з базовими скриптами оболонки, існує багато альтернативних мов програмування, які також використовують регулярні вирази, такі як Python, JavaScript та Ruby. 

Щодо реалізації, Bash використовує доволі стару версію регулярних виразів, яка може не включати деякі сучасні особливості або висловлювання, доступні в інших мовах.

## Додатково:

1. [Bash Guide for Beginners](https://www.bash.academy/)
2. [Regex Tutorial - A quick cheatsheet by examples](https://www.factorypattern.co.uk/blog/regex-tutorial-a-quick-cheatsheet-by-examples/)
3. [GNU Bash Manual - Pattern Matching](https://www.gnu.org/software/bash/manual/html_node/Pattern-Matching.html)