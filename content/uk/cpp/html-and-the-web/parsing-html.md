---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:01.262218-07:00
description: "\u0410\u043D\u0430\u043B\u0456\u0437 HTML \u043F\u043E\u043B\u044F\u0433\
  \u0430\u0454 \u0432 \u0440\u043E\u0437\u0431\u0438\u0442\u0442\u0456 HTML-\u0432\
  \u043C\u0456\u0441\u0442\u0443 \u043D\u0430 \u0449\u043E\u0441\u044C, \u0449\u043E\
  \ \u043F\u0440\u043E\u0433\u0440\u0430\u043C\u0430 \u043C\u043E\u0436\u0435 \u0440\
  \u043E\u0437\u0443\u043C\u0456\u0442\u0438 \u0442\u0430 \u043C\u0430\u043D\u0456\
  \u043F\u0443\u043B\u044E\u0432\u0430\u0442\u0438. \u041F\u0440\u043E\u0433\u0440\
  \u0430\u043C\u0456\u0441\u0442\u0438 \u0440\u043E\u0431\u043B\u044F\u0442\u044C\
  \ \u0446\u0435 \u0434\u043B\u044F \u0432\u0438\u0442\u044F\u0433\u0443 \u0434\u0430\
  \u043D\u0438\u0445, \u043C\u0430\u043D\u0456\u043F\u0443\u043B\u044F\u0446\u0456\
  \u0439 \u0437\u2026"
lastmod: '2024-03-13T22:44:49.839339-06:00'
model: gpt-4-0125-preview
summary: "\u0410\u043D\u0430\u043B\u0456\u0437 HTML \u043F\u043E\u043B\u044F\u0433\
  \u0430\u0454 \u0432 \u0440\u043E\u0437\u0431\u0438\u0442\u0442\u0456 HTML-\u0432\
  \u043C\u0456\u0441\u0442\u0443 \u043D\u0430 \u0449\u043E\u0441\u044C, \u0449\u043E\
  \ \u043F\u0440\u043E\u0433\u0440\u0430\u043C\u0430 \u043C\u043E\u0436\u0435 \u0440\
  \u043E\u0437\u0443\u043C\u0456\u0442\u0438 \u0442\u0430 \u043C\u0430\u043D\u0456\
  \u043F\u0443\u043B\u044E\u0432\u0430\u0442\u0438."
title: "\u0410\u043D\u0430\u043B\u0456\u0437 HTML"
weight: 43
---

## Як це зробити:
C++ не має вбудованих можливостей для аналізу HTML. Зазвичай ви використовуєте бібліотеку, як-от Gumbo-parser від Google, або щось подібне. Ось швидкий приклад використання Gumbo-parser:

```C++
#include <iostream>
#include <gumbo.h>

void search_for_links(GumboNode* node) {
    if (node->type != GUMBO_NODE_ELEMENT) {
        return;
    }
    if (node->v.element.tag == GUMBO_TAG_A) {
        GumboAttribute* href = gumbo_get_attribute(&node->v.element.attributes, "href");
        if (href) {
            std::cout << href->value << std::endl;
        }
    }
    GumboVector* children = &node->v.element.children;
    for (unsigned int i = 0; i < children->length; ++i) {
        search_for_links(static_cast<GumboNode*>(children->data[i]));
    }
}

int main() {
    const char* html = "<html><body><a href='https://example.com'>Link</a></body></html>";
    GumboOutput* output = gumbo_parse(html);
    search_for_links(output->root);
    gumbo_destroy_output(&kGumboDefaultOptions, output);
    return 0;
}
```

Приклад виводу:
```
https://example.com
```

## Поглиблений аналіз
Аналіз HTML завжди не був простим завданням в C++. Історично програмісти використовували regex або написані вручну парсери, обидва з яких схильні до помилок і громіздкі. На сьогодні, надійні бібліотеки, як-от Gumbo-parser, вирішують складнощі парсингу, роблячи це легшим і надійнішим.

Альтернативи включають Tidy, MyHTML, або навіть інтеграцію C++ з Python's BeautifulSoup через функцію `system` C++ або вбудовані інтерпретатори.

З точки зору імплементації, ці бібліотеки конвертують HTML в дерево Document Object Model (DOM). Проходження та маніпуляція з DOM дозволяє користувачам витягувати та працювати з даними, як показано в розділі Як це зробити.

## Дивіться також
- [Репозиторій Gumbo-parser на GitHub](https://github.com/google/gumbo-parser)
- [Список бібліотек для аналізу HTML](https://en.cppreference.com/w/c/experimental/dynamic)
- [Взаємодія C++ та Python](https://docs.python.org/3/extending/embedding.html)
