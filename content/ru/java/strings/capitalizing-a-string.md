---
aliases:
- /ru/java/capitalizing-a-string/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:55:48.241046-07:00
description: "\u041F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\u043E\u0432\u0430\u043D\
  \u0438\u0435 \u0441\u0442\u0440\u043E\u043A\u0438 \u0432 \u0437\u0430\u0433\u043E\
  \u043B\u043E\u0432\u043E\u0447\u043D\u044B\u0439 \u0440\u0435\u0433\u0438\u0441\u0442\
  \u0440 \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u0438\u0437\u043C\u0435\
  \u043D\u0435\u043D\u0438\u0435 \u043F\u0435\u0440\u0432\u043E\u0439 \u0431\u0443\
  \u043A\u0432\u044B \u043D\u0430 \u0437\u0430\u0433\u043B\u0430\u0432\u043D\u0443\
  \u044E, \u0430 \u043E\u0441\u0442\u0430\u043B\u044C\u043D\u044B\u0445 \u043D\u0430\
  \ \u0441\u0442\u0440\u043E\u0447\u043D\u044B\u0435. \u041F\u0440\u043E\u0433\u0440\
  \u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0438\u0441\u043F\u043E\u043B\u044C\u0437\
  \u0443\u044E\u0442 \u044D\u0442\u043E \u0434\u043B\u044F\u2026"
lastmod: 2024-02-18 23:08:56.817893
model: gpt-4-0125-preview
summary: "\u041F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\u043E\u0432\u0430\u043D\
  \u0438\u0435 \u0441\u0442\u0440\u043E\u043A\u0438 \u0432 \u0437\u0430\u0433\u043E\
  \u043B\u043E\u0432\u043E\u0447\u043D\u044B\u0439 \u0440\u0435\u0433\u0438\u0441\u0442\
  \u0440 \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u0438\u0437\u043C\u0435\
  \u043D\u0435\u043D\u0438\u0435 \u043F\u0435\u0440\u0432\u043E\u0439 \u0431\u0443\
  \u043A\u0432\u044B \u043D\u0430 \u0437\u0430\u0433\u043B\u0430\u0432\u043D\u0443\
  \u044E, \u0430 \u043E\u0441\u0442\u0430\u043B\u044C\u043D\u044B\u0445 \u043D\u0430\
  \ \u0441\u0442\u0440\u043E\u0447\u043D\u044B\u0435. \u041F\u0440\u043E\u0433\u0440\
  \u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0438\u0441\u043F\u043E\u043B\u044C\u0437\
  \u0443\u044E\u0442 \u044D\u0442\u043E \u0434\u043B\u044F\u2026"
title: "\u041F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\u043E\u0432\u0430\u043D\u0438\
  \u0435 \u0441\u0442\u0440\u043E\u043A\u0438 \u0432 \u0432\u0435\u0440\u0445\u043D\
  \u0438\u0439 \u0440\u0435\u0433\u0438\u0441\u0442\u0440"
---

{{< edit_this_page >}}

## Что и Почему?

Преобразование строки в заголовочный регистр означает изменение первой буквы на заглавную, а остальных на строчные. Программисты используют это для стандартизации текстовых данных, таких как ввод пользователя или имена, обеспечивая консистентность по всему набору данных.

## Как:

В Java нет встроенного метода для полного преобразования строки в заголовочный регистр (первая буква в верхнем регистре, остальные в нижнем), но вот быстрый способ сделать именно это:

```java
public class StringCapitalizer {
    public static void main(String[] args) {
        String input = "java is fun!"; // пример строки
        String output = capitalizeString(input);
        System.out.println(output); // Java is fun!
    }

    public static String capitalizeString(String str) {
        if(str == null || str.isEmpty()) {
            return str;
        }
        return str.substring(0, 1).toUpperCase() + str.substring(1).toLowerCase();
    }
}
```

## Погружение

До Java 8 вышеописанный метод был обычным способом преобразования строки в заголовочный регистр. С введением потоков (streams) в Java 8 мы также можем манипулировать строками с большей гибкостью.

Альтернативный способ использования потоков для преобразования:

```java
import java.util.stream.*;

public class StringCapitalizer {
    public static void main(String[] args) {
        String input = "java is cool!";
        String output = Arrays.stream(input.split("\\s"))
                              .map(word -> word.substring(0, 1).toUpperCase() + word.substring(1).toLowerCase())
                              .collect(Collectors.joining(" "));
        System.out.println(output); // Java Is Cool!
    }
}
```

Это разделяет строку на слова, преобразует каждое в заголовочный регистр и соединяет обратно вместе. Обратите внимание на различие: каждое слово преобразуется, а не только первое.

Строки в Java являются неизменяемыми, то есть, как только они созданы, они не могут измениться. Методы, которые кажется изменяют строки, наподобие `toUpperCase` или `toLowerCase`, на самом деле создают новые строки с применёнными изменениями.

С точки зрения производительности, для манипуляции со строками часто используется StringBuilder, поскольку он изменяем. Это позволяет избежать затрат на создание множества объектов строк. Однако для простого преобразования заглавных букв прирост производительности не является значительным, поэтому пример с `StringBuilder` пропущен.

## См. также

- [Документация по API строк Java](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)
- [Документация по Collector](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Collectors.html)
- [Документация по StringJoiner](https://docs.oracle.com/javase/8/docs/api/java/util/StringJoiner.html)
