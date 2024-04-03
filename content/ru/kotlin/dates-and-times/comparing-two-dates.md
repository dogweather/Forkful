---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:55:50.287265-07:00
description: "\u0421\u0440\u0430\u0432\u043D\u0435\u043D\u0438\u0435 \u0434\u0432\u0443\
  \u0445 \u0434\u0430\u0442 \u043F\u043E\u0434\u0440\u0430\u0437\u0443\u043C\u0435\
  \u0432\u0430\u0435\u0442 \u043F\u0440\u043E\u0432\u0435\u0440\u043A\u0443, \u043F\
  \u0440\u0435\u0434\u0448\u0435\u0441\u0442\u0432\u0443\u0435\u0442 \u043B\u0438\
  \ \u043E\u0434\u043D\u0430 \u0438\u0437 \u043D\u0438\u0445 \u0434\u0440\u0443\u0433\
  \u043E\u0439, \u0441\u043B\u0435\u0434\u0443\u0435\u0442 \u0437\u0430 \u043D\u0435\
  \u0439 \u0438\u043B\u0438 \u043E\u043D\u0438 \u0441\u043E\u043E\u0442\u0432\u0435\
  \u0442\u0441\u0442\u0432\u0443\u044E\u0442 \u043E\u0434\u043D\u043E\u043C\u0443\
  \ \u0438 \u0442\u043E\u043C\u0443 \u0436\u0435 \u043C\u043E\u043C\u0435\u043D\u0442\
  \u0443 \u0432\u0440\u0435\u043C\u0435\u043D\u0438.\u2026"
lastmod: '2024-03-13T22:44:45.001947-06:00'
model: gpt-4-0125-preview
summary: "\u0421\u0440\u0430\u0432\u043D\u0435\u043D\u0438\u0435 \u0434\u0432\u0443\
  \u0445 \u0434\u0430\u0442 \u043F\u043E\u0434\u0440\u0430\u0437\u0443\u043C\u0435\
  \u0432\u0430\u0435\u0442 \u043F\u0440\u043E\u0432\u0435\u0440\u043A\u0443, \u043F\
  \u0440\u0435\u0434\u0448\u0435\u0441\u0442\u0432\u0443\u0435\u0442 \u043B\u0438\
  \ \u043E\u0434\u043D\u0430 \u0438\u0437 \u043D\u0438\u0445 \u0434\u0440\u0443\u0433\
  \u043E\u0439, \u0441\u043B\u0435\u0434\u0443\u0435\u0442 \u0437\u0430 \u043D\u0435\
  \u0439 \u0438\u043B\u0438 \u043E\u043D\u0438 \u0441\u043E\u043E\u0442\u0432\u0435\
  \u0442\u0441\u0442\u0432\u0443\u044E\u0442 \u043E\u0434\u043D\u043E\u043C\u0443\
  \ \u0438 \u0442\u043E\u043C\u0443 \u0436\u0435 \u043C\u043E\u043C\u0435\u043D\u0442\
  \u0443 \u0432\u0440\u0435\u043C\u0435\u043D\u0438."
title: "\u0421\u0440\u0430\u0432\u043D\u0435\u043D\u0438\u0435 \u0434\u0432\u0443\u0445\
  \ \u0434\u0430\u0442"
weight: 27
---

## Как сделать:
```Kotlin
import java.time.LocalDate

fun main() {
    val date1 = LocalDate.of(2023, 4, 10)
    val date2 = LocalDate.of(2023, 5, 15)

    println(date1.isBefore(date2))  // true
    println(date1.isAfter(date2))   // false
    println(date1.isEqual(date2))   // false

    // Сравнение с использованием compareTo
    println(date1.compareTo(date2)) // -1, если date1 предшествует date2
}
```

Пример вывода:

```
true
false
false
-1
```

## Подробнее
Исторически, Java предоставляла классы `Date` и `Calendar`, но они были не очень удобны в использовании. Kotlin использует аналогичные классы «под капотом», но рекомендует использовать пакет `java.time`, введенный в Java 8, для большей ясности и пользы.

Существуют альтернативы, такие как `Instant` для временных меток, `ZonedDateTime` для дат, специфических для часовых поясов, или использование сторонних библиотек, как Joda-Time. Имейте в виду детали реализации - `Instant` использует традиционную временную метку Unix, в то время как `LocalDate` абстрагируется от этого и работает с понятием дня без времени или часового пояса.

Знание, какой класс лучше всего подходит для ваших потребностей, является ключевым. `LocalDate` подходит для большинства сравнений дат, но для точного сравнения моментов времени стоит рассмотреть `ZonedDateTime` или `Instant`.

## См. также
- Официальная документация Kotlin по датам и времени: [https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.time/](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.time/)
- Руководство Java 8 по дате и времени: [https://www.oracle.com/technical-resources/articles/java/jf14-date-time.html](https://www.oracle.com/technical-resources/articles/java/jf14-date-time.html)
- Библиотека Joda-Time: [https://www.joda.org/joda-time/](https://www.joda.org/joda-time/)
