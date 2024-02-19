---
aliases:
- /uk/haskell/comparing-two-dates/
date: 2024-01-20 17:33:38.249737-07:00
description: "\u041F\u043E\u0440\u0456\u0432\u043D\u044E\u0454\u043C\u043E \u0434\u0432\
  \u0456 \u0434\u0430\u0442\u0438, \u0449\u043E\u0431 \u0432\u0438\u0437\u043D\u0430\
  \u0447\u0438\u0442\u0438, \u044F\u043A\u0430 \u0437 \u043D\u0438\u0445 \u0440\u0430\
  \u043D\u0456\u0448\u0435 \u0447\u0438 \u043F\u0456\u0437\u043D\u0456\u0448\u0435\
  , \u0430\u0431\u043E \u0447\u0438 \u0432\u043E\u043D\u0438 \u043E\u0434\u043D\u0430\
  \u043A\u043E\u0432\u0456. \u0423 \u043F\u0440\u043E\u0433\u0440\u0430\u043C\u0443\
  \u0432\u0430\u043D\u043D\u0456 \u0446\u0435 \u0432\u0430\u0436\u043B\u0438\u0432\
  \u043E \u0434\u043B\u044F \u043E\u0431\u0440\u043E\u0431\u043A\u0438 \u0442\u0435\
  \u0440\u043C\u0456\u043D\u0456\u0432, \u043F\u043B\u0430\u043D\u0443\u0432\u0430\
  \u043D\u043D\u044F\u2026"
lastmod: 2024-02-18 23:09:00.440340
model: gpt-4-1106-preview
summary: "\u041F\u043E\u0440\u0456\u0432\u043D\u044E\u0454\u043C\u043E \u0434\u0432\
  \u0456 \u0434\u0430\u0442\u0438, \u0449\u043E\u0431 \u0432\u0438\u0437\u043D\u0430\
  \u0447\u0438\u0442\u0438, \u044F\u043A\u0430 \u0437 \u043D\u0438\u0445 \u0440\u0430\
  \u043D\u0456\u0448\u0435 \u0447\u0438 \u043F\u0456\u0437\u043D\u0456\u0448\u0435\
  , \u0430\u0431\u043E \u0447\u0438 \u0432\u043E\u043D\u0438 \u043E\u0434\u043D\u0430\
  \u043A\u043E\u0432\u0456. \u0423 \u043F\u0440\u043E\u0433\u0440\u0430\u043C\u0443\
  \u0432\u0430\u043D\u043D\u0456 \u0446\u0435 \u0432\u0430\u0436\u043B\u0438\u0432\
  \u043E \u0434\u043B\u044F \u043E\u0431\u0440\u043E\u0431\u043A\u0438 \u0442\u0435\
  \u0440\u043C\u0456\u043D\u0456\u0432, \u043F\u043B\u0430\u043D\u0443\u0432\u0430\
  \u043D\u043D\u044F\u2026"
title: "\u041F\u043E\u0440\u0456\u0432\u043D\u044F\u043D\u043D\u044F \u0434\u0432\u043E\
  \u0445 \u0434\u0430\u0442"
---

{{< edit_this_page >}}

## Що та чому?
Порівнюємо дві дати, щоб визначити, яка з них раніше чи пізніше, або чи вони однакові. У програмуванні це важливо для обробки термінів, планування заходів, ведення журналів тощо.

## Як це зробити:
```Haskell
import Data.Time

-- Порівнюємо дві дати
compareDates :: IO ()
compareDates = do
    let date1 = fromGregorian 2023 3 15 -- 15 березня 2023
    let date2 = fromGregorian 2023 10 19 -- 19 жовтня 2023
    let comparisonResult = compare date1 date2
    printResult comparisonResult

-- Друкуємо результат порівняння
printResult :: Ordering -> IO ()
printResult GT = putStrLn "Перша дата пізніше другої."
printResult LT = putStrLn "Перша дата раніше другої."
printResult EQ = putStrLn "Дати однакові."

main :: IO ()
main = compareDates
```
Виведення:
```
Перша дата раніше другої.
```

## Поглиблений аналіз:
У Haskell, порівняння дат засноване на типі `UTCTime` з пакету `time`, який вже давно є стандартом для обробки часу і дат. Альтернативи включають сторонні бібліотеки як `thyme` чи `chronos`, але `time` найчастіше за все вповні покриває потреби розробників.

Функція `fromGregorian` використовує Григоріанський календар, dominantly used since 1582, and the `compare` function can directly compare two dates. The result is of the type `Ordering`, with possible values `GT` (greater than), `LT` (less than), or `EQ` (equal to).

Детальнішу інформацію про обробку дат і часу в Haskell можна знайти в офіційній документації пакету `time`.

## Додатково:
- Офіційна документація `time`: [https://hackage.haskell.org/package/time](https://hackage.haskell.org/package/time)
