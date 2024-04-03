---
date: 2024-01-20 17:58:06.142235-07:00
description: "\u041F\u043E\u0448\u0443\u043A \u0442\u0430 \u0437\u0430\u043C\u0456\
  \u043D\u0430 \u0442\u0435\u043A\u0441\u0442\u0443 \u2014 \u0446\u0435 \u0437\u0430\
  \u0441\u0456\u0431 \u043E\u0431\u0440\u043E\u0431\u043A\u0438 \u0440\u044F\u0434\
  \u043A\u0456\u0432, \u0449\u043E \u0434\u043E\u0437\u0432\u043E\u043B\u044F\u0454\
  \ \u0437\u043D\u0430\u0445\u043E\u0434\u0438\u0442\u0438 \u0444\u0440\u0430\u0433\
  \u043C\u0435\u043D\u0442\u0438 \u0442\u0435\u043A\u0441\u0442\u0443 \u0442\u0430\
  \ \u0437\u0430\u043C\u0456\u043D\u044E\u0432\u0430\u0442\u0438 \u0457\u0445 \u043D\
  \u0430 \u0456\u043D\u0448\u0456. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\
  \u0441\u0442\u0438 \u0440\u043E\u0431\u043B\u044F\u0442\u044C \u0446\u0435 \u0434\
  \u043B\u044F\u2026"
lastmod: '2024-03-13T22:44:49.332637-06:00'
model: gpt-4-1106-preview
summary: "\u041F\u043E\u0448\u0443\u043A \u0442\u0430 \u0437\u0430\u043C\u0456\u043D\
  \u0430 \u0442\u0435\u043A\u0441\u0442\u0443 \u2014 \u0446\u0435 \u0437\u0430\u0441\
  \u0456\u0431 \u043E\u0431\u0440\u043E\u0431\u043A\u0438 \u0440\u044F\u0434\u043A\
  \u0456\u0432, \u0449\u043E \u0434\u043E\u0437\u0432\u043E\u043B\u044F\u0454 \u0437\
  \u043D\u0430\u0445\u043E\u0434\u0438\u0442\u0438 \u0444\u0440\u0430\u0433\u043C\u0435\
  \u043D\u0442\u0438 \u0442\u0435\u043A\u0441\u0442\u0443 \u0442\u0430 \u0437\u0430\
  \u043C\u0456\u043D\u044E\u0432\u0430\u0442\u0438 \u0457\u0445 \u043D\u0430 \u0456\
  \u043D\u0448\u0456."
title: "\u041F\u043E\u0448\u0443\u043A \u0442\u0430 \u0437\u0430\u043C\u0456\u043D\
  \u0430 \u0442\u0435\u043A\u0441\u0442\u0443"
weight: 10
---

## Як це зробити:
```Haskell
import Data.Text as T

-- Пошук та заміна простим текстом
replaceText :: String -> String -> String -> String
replaceText old new = T.unpack . T.replace (T.pack old) (T.pack new) . T.pack

-- Використання функції
main = putStrLn $ replaceText "cat" "dog" "The cat sat on the mat"

-- Результат:
-- "The dog sat on the mat"
```
Для регулярних виразів використовуємо `Text.Regex`:
```Haskell
import Text.Regex

-- Пошук та заміна за допомогою регулярних виразів
replaceRegex :: String -> String -> String -> String
replaceRegex regex new input =
  let compiledRegex = mkRegex regex
  in subRegex compiledRegex input new

-- Використання функції
main = putStrLn $ replaceRegex "c.t" "dog" "The cat sat on the mat"

-- Результат:
-- "The dog sat on the mat"
```

## Поглиблений розділ:
Пошук та заміна тексту бере свій початок ще від ранніх редакторів тексту, таких як `ed` і `sed` у Unix. Ці інструменти використовувались для роботи з текстовими файлами за допомогою командного рядка. У Haskell ми маємо ряд бібліотек, що надають функціональність для пошуку та заміни, включаючи `Data.Text` для простого тексту та `Text.Regex` при роботі з регулярними виразами.

Головна альтернатива — це використання стандартної бібліотеки `Prelude` з її функціями для роботи з рядками, але `Data.Text` пропонує покращену продуктивність з великими текстами.

Для регулярних виразів популярною альтернативою є `regex-pcre-builtin`, що використовує бібліотеку PCRE для мови Haskell, надаючи більш розширений синтаксис та контроль.

## Дивись також:
- [Документація для модуля Data.Text](https://hackage.haskell.org/package/text-1.2.4.1/docs/Data-Text.html)
- [Документація для Text.Regex](https://hackage.haskell.org/package/regex-compat-0.95.1/docs/Text-Regex.html)
- [An introduction to regex in Haskell](https://wiki.haskell.org/Regular_expressions)
- [Інформація про регулярні вирази PCRE](http://www.pcre.org)
