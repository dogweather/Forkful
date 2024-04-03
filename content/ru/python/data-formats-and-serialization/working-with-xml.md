---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:15.528440-07:00
description: "\"\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 XML\" \u043E\u0442\u043D\
  \u043E\u0441\u0438\u0442\u0441\u044F \u043A \u043F\u0440\u043E\u0446\u0435\u0441\
  \u0441\u0443 \u0447\u0442\u0435\u043D\u0438\u044F, \u0441\u043E\u0437\u0434\u0430\
  \u043D\u0438\u044F \u0438 \u0438\u0437\u043C\u0435\u043D\u0435\u043D\u0438\u044F\
  \ \u0444\u0430\u0439\u043B\u043E\u0432 XML (eXtensible Markup Language) \u0441 \u0438\
  \u0441\u043F\u043E\u043B\u044C\u0437\u043E\u0432\u0430\u043D\u0438\u0435\u043C \u043F\
  \u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0440\u043E\u0432\u0430\u043D\u0438\
  \u044F. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B\
  \u2026"
lastmod: '2024-03-13T22:44:44.316628-06:00'
model: gpt-4-0125-preview
summary: "\"\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 XML\" \u043E\u0442\u043D\u043E\
  \u0441\u0438\u0442\u0441\u044F \u043A \u043F\u0440\u043E\u0446\u0435\u0441\u0441\
  \u0443 \u0447\u0442\u0435\u043D\u0438\u044F, \u0441\u043E\u0437\u0434\u0430\u043D\
  \u0438\u044F \u0438 \u0438\u0437\u043C\u0435\u043D\u0435\u043D\u0438\u044F \u0444\
  \u0430\u0439\u043B\u043E\u0432 XML (eXtensible Markup Language) \u0441 \u0438\u0441\
  \u043F\u043E\u043B\u044C\u0437\u043E\u0432\u0430\u043D\u0438\u0435\u043C \u043F\u0440\
  \u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u044F\
  ."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 XML"
weight: 40
---

## Как:
Модуль Python `xml.etree.ElementTree` предлагает инструменты для работы с XML.

Разбор XML-документа:
```python
import xml.etree.ElementTree as ET

xml_data = """<?xml version="1.0"?>
<библиотека>
    <книга>
        <название>Изучаем Python</название>
        <автор>Марк Лутц</автор>
    </книга>
    <книга>
        <название>Программирование на Python</название>
        <автор>Марк Лутц</автор>
    </книга>
</библиотека>
"""

root = ET.fromstring(xml_data)
for book in root.findall('книга'):
    title = book.find('название').text
    author = book.find('автор').text
    print(f'Название: {title}, Автор: {author}')
```
Пример вывода:
```
Название: Изучаем Python, Автор: Марк Лутц
Название: Программирование на Python, Автор: Марк Лутц
```

Создание XML-документа:
```python
library = ET.Element('библиотека')
book = ET.SubElement(library, 'книга')
title = ET.SubElement(book, 'название')
title.text = 'Автоматизация скучной работы с помощью Python'
author = ET.SubElement(book, 'автор')
author.text = 'Ал Свейгарт'

tree = ET.ElementTree(library)
tree.write('library.xml')
```

## Подробнее:
XML существует с конца 90-х годов, созданный как упрощенное подмножество SGML для удобного обмена данными онлайн. Несмотря на растущую популярность JSON для веб-данных, XML остаётся жизненно важным во многих предприятиях, конфигурациях и веб-сервисах (SOAP, RSS).

Альтернативы `xml.etree.ElementTree` включают в себя `lxml` и `minidom`. `lxml` работает быстрее и имеет больше функций, в то время как `minidom` предоставляет более "DOM-подобный" интерфейс XML. При выборе учитывайте удобство использования, производительность и конкретные требования к функционалу.

Под капотом `ElementTree` работает на модели дерева элементов, где каждый компонент XML-файла является узлом в дереве. Это позволяет использовать простые выражения путей и поиски, делая навигацию и манипуляцию структурой данных XML проще.

## См. также:
- Модуль Python `xml.etree.ElementTree`: https://docs.python.org/3/library/xml.etree.elementtree.html
- `lxml`: https://lxml.de/
- Учебник XML от W3Schools: https://www.w3schools.com/xml/
- Спецификация XML: https://www.w3.org/XML/
