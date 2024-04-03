---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:56:49.696024-07:00
description: "\u041A\u043E\u043D\u043A\u0430\u0442\u0435\u043D\u0430\u0446\u0438\u044F\
  \ \u0441\u0442\u0440\u043E\u043A \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442\
  \ \u0438\u0445 \u0441\u043B\u0438\u044F\u043D\u0438\u0435 \u0432\u0441\u0442\u044B\
  \u043A. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B\
  \ \u0434\u0435\u043B\u0430\u044E\u0442 \u044D\u0442\u043E, \u043A\u043E\u0433\u0434\
  \u0430 \u0438\u043C \u043D\u0443\u0436\u043D\u043E \u0441\u043E\u0435\u0434\u0438\
  \u043D\u0438\u0442\u044C \u0447\u0430\u0441\u0442\u0438 \u0442\u0435\u043A\u0441\
  \u0442\u0430 \u0432 \u043D\u043E\u0432\u0443\u044E \u0441\u0442\u0440\u043E\u043A\
  \u0443, \u043D\u0430\u043F\u0440\u0438\u043C\u0435\u0440, \u0434\u043B\u044F \u0433\
  \u0435\u043D\u0435\u0440\u0430\u0446\u0438\u0438\u2026"
lastmod: '2024-03-13T22:44:45.118743-06:00'
model: gpt-4-0125-preview
summary: "\u041A\u043E\u043D\u043A\u0430\u0442\u0435\u043D\u0430\u0446\u0438\u044F\
  \ \u0441\u0442\u0440\u043E\u043A \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442\
  \ \u0438\u0445 \u0441\u043B\u0438\u044F\u043D\u0438\u0435 \u0432\u0441\u0442\u044B\
  \u043A."
title: "\u0421\u043A\u043B\u0435\u0438\u0432\u0430\u043D\u0438\u0435 \u0441\u0442\u0440\
  \u043E\u043A"
weight: 3
---

## Как это сделать:
В Haskell конкатенация строк довольно проста с оператором `(++)`:

```Haskell
main :: IO ()
main = do
  let hello = "Привет"
  let world = "Мир!"

  -- Использование оператора (++)
  putStrLn $ hello ++ " " ++ world

  -- Пример вывода: "Привет Мир!"
```

Но почему останавливаться на этом? У вас также есть `concat` и `intercalate` из `Data.List`, когда дело доходит до списков:

```Haskell
import Data.List (intercalate, concat)

main :: IO ()
main = do
  let wordsList = ["Haskell", "это", "круто"]

  -- Конкатенация списка строк
  putStrLn $ concat wordsList
  -- Пример вывода: "Haskellэтокруто"

  -- Вставка строк с разделителем
  putStrLn $ intercalate " " wordsList
  -- Пример вывода: "Haskell это круто"
```

## Глубокое Погружение
В прошлом оператор `++` в Haskell брал вдохновение из похожих операций в языках вроде ML. Это классика, но не всегда самый эффективный метод, особенно для больших строк или массовых задач по конкатенации. Каждое использование `++` создает новый список, что означает, если вы работаете с большими данными, вам может понадобиться более эффективный подход.

Альтернативы? Безусловно. Тип `Builder` из `Data.Text.Lazy.Builder` может быть лучше оптимизирован для крупномасштабных текстовых манипуляций. Он конструирует текст более экономно, работая блоками, уменьшая необходимость постоянного копирования всего.

Например, работа с `Builder`:

```Haskell
import Data.Text.Lazy.Builder (Builder, fromString, toLazyText)
import Data.Text.Lazy.IO as T

main :: IO ()
main = do
  let builder1 = fromString "Haskell"
  let builder2 = fromString " "
  let builder3 = fromString "это"
  let builder4 = fromString " "
  let builder5 = fromString "классно!"

  let result = mconcat [builder1, builder2, builder3, builder4, builder5]
  -- Использование mconcat для слияния Builder'ов

  T.putStrLn $ toLazyText result
  -- Пример вывода: "Haskell это классно!"
```

Почему стоит использовать `Builder` или `concat`? Они обрабатывают большие объемы данных без проблем, позволяя объединять текст без потери производительности.

## Смотрите Также
- Haskell Wiki о [Performance/Strings](https://wiki.haskell.org/Performance/Strings) для более глубокого погружения в вопросы производительности.
- Документация пакета `Data.Text` [package documentation](https://hackage.haskell.org/package/text) для работы с текстом Unicode в Haskell.
- [Веб-сайт языка Haskell](https://www.haskell.org/), чтобы быть в курсе всего, что касается Haskell.
