---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:01.933435-07:00
description: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 XML \u0432 Haskell \u0432\
  \u043A\u043B\u044E\u0447\u0430\u0435\u0442 \u0432 \u0441\u0435\u0431\u044F \u0430\
  \u043D\u0430\u043B\u0438\u0437, \u043C\u0430\u043D\u0438\u043F\u0443\u043B\u0438\
  \u0440\u043E\u0432\u0430\u043D\u0438\u0435 \u0438 \u0433\u0435\u043D\u0435\u0440\
  \u0430\u0446\u0438\u044E \u0441\u0442\u0440\u0443\u043A\u0442\u0443\u0440 XML. \u041F\
  \u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0443\u043F\u0440\
  \u0430\u0432\u043B\u044F\u044E\u0442 XML \u0434\u043B\u044F \u0432\u0437\u0430\u0438\
  \u043C\u043E\u0434\u0435\u0439\u0441\u0442\u0432\u0438\u044F \u0441 \u043C\u043D\
  \u043E\u0436\u0435\u0441\u0442\u0432\u043E\u043C\u2026"
lastmod: '2024-03-13T22:44:45.176909-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 XML \u0432 Haskell \u0432\u043A\
  \u043B\u044E\u0447\u0430\u0435\u0442 \u0432 \u0441\u0435\u0431\u044F \u0430\u043D\
  \u0430\u043B\u0438\u0437, \u043C\u0430\u043D\u0438\u043F\u0443\u043B\u0438\u0440\
  \u043E\u0432\u0430\u043D\u0438\u0435 \u0438 \u0433\u0435\u043D\u0435\u0440\u0430\
  \u0446\u0438\u044E \u0441\u0442\u0440\u0443\u043A\u0442\u0443\u0440 XML."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 XML"
weight: 40
---

## Как это сделать:
Haskell предлагает библиотеки, например, `xml-conduit`, для работы с XML. Следующий пример демонстрирует анализ строки XML и запрос элементов:

```haskell
{-# LANGUAGE OverloadedStrings #-}

import qualified Data.Text as T
import Text.XML
import Text.XML.Cursor

main :: IO ()
main = do
  let xmlContent = "<greetings><hello>World!</hello></greetings>"
  let document = parseLBS_ def $ T.encodeUtf8 $ T.pack xmlContent
  let cursor = fromDocument document

  let helloTexts = cursor $// element "hello" &/ content
  print helloTexts  -- ['World!']
```

Пример вывода:

```
["World!"]
```

## Подробнее
XML, что означает eXtensible Markup Language (расширяемый язык разметки), давно является стандартом сериализации данных, ещё до восхода JSON. Он многословен, но жёсткий и стандартизированный, что делает его подходящим для строгих корпоративных сред, устаревших систем и отраслей, таких как финансы и здравоохранение.

Haskell имеет несколько библиотек для работы с XML; однако, `xml-conduit` является одной из самых мощных и широко используемых благодаря своим эффективным возможностям потоковой передачи и парсинга, являясь частью семейства `conduit` для обработки потоков данных.

Альтернативой является `HXT` (Haskell XML Toolbox), который использует стрелки для парсинга и преобразования, предлагая другую парадигму для манипуляций с XML. Хотя `HXT` сейчас менее популярен из-за его более крутой кривой обучения, он всё ещё остаётся надёжным выбором для некоторых случаев использования.

При реализации обработки XML в Haskell, вам нужно будет заботиться об кодировке, так как строки в Haskell являются Unicode, а данные XML могут не быть таковыми. К тому же, пространства имён XML могут добавить дополнительную сложность к анализу.

## См. также:
- Документация пакета `xml-conduit`: https://hackage.haskell.org/package/xml-conduit
- Haskell XML Toolbox (HXT): http://hackage.haskell.org/package/hxt
- Книга "Real World Haskell", Глава 16, по обработке XML: http://book.realworldhaskell.org/read/xml.html
- Вики Haskell по XML: https://wiki.haskell.org/XML
