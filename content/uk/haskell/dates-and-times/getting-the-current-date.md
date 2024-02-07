---
title:                "Отримання поточної дати"
date:                  2024-02-03T19:09:57.848906-07:00
model:                 gpt-4-0125-preview
simple_title:         "Отримання поточної дати"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/haskell/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Що та Чому?
Отримання поточної дати в Haskell полягає у визначенні поточного часу системи та його перетворення в зрозумілий формат дати. Програмісти роблять це для виконання операцій на основі дати, таких як ведення журналу, планування завдань або маркування подій у програмах за часом.

## Як:
Стандартна бібліотека Haskell, `base`, надає модуль `Data.Time`, який пропонує функціональність для роботи з датами та часом. Ось як використовувати його для отримання поточної дати:

```haskell
import Data.Time (getCurrentTime, utctDay)

main :: IO ()
main = do
    now <- getCurrentTime
    let today = utctDay now
    print today
```

Приклад виводу:
```
2023-04-12
```

Для більшої гнучкості, наприклад, форматування дати або роботи з різними часовими зонами, бібліотека `time` є незамінною. Ось як ви можете форматувати поточну дату:

```haskell
import Data.Time

main :: IO ()
main = do
    now <- getCurrentTime
    timezone <- getCurrentTimeZone
    let zoneNow = utcToLocalTime timezone now
    putStrLn $ formatTime defaultTimeLocale "%Y-%m-%d" zoneNow
```

Це виводить поточну дату у форматі `YYYY-MM-DD`, коригованій до локальної часової зони.

Крім того, для підтримки сторонніх бібліотек, `time` сильно рекомендується та часто використовується в спільноті Haskell завдяки своїм широким можливостям маніпуляції з датами та часом. Приклади вище використовують цю бібліотеку.

Якщо вам потрібне більш всебічне маніпулювання датами, включаючи парсинг з рядків або арифметичні операції з датами та часом, дослідження додаткових функцій у `Data.Time` буде корисним.
