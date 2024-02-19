---
aliases:
- /ru/kotlin/parsing-a-date-from-a-string/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:00:19.676753-07:00
description: "\u0420\u0430\u0437\u0431\u043E\u0440 \u0434\u0430\u0442\u044B \u043E\
  \u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u043F\u0440\u0435\u043E\u0431\u0440\u0430\
  \u0437\u043E\u0432\u0430\u043D\u0438\u0435 \u0434\u0430\u0442\u044B \u0438\u0437\
  \ \u0442\u0435\u043A\u0441\u0442\u043E\u0432\u043E\u0433\u043E \u0444\u043E\u0440\
  \u043C\u0430\u0442\u0430 \u0432 \u043E\u0431\u044A\u0435\u043A\u0442 \u0434\u0430\
  \u0442\u044B, \u043A\u043E\u0442\u043E\u0440\u044B\u0439 \u043F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u043C\u0430 \u043C\u043E\u0436\u0435\u0442 \u043F\u043E\u043D\
  \u0438\u043C\u0430\u0442\u044C \u0438 \u043C\u0430\u043D\u0438\u043F\u0443\u043B\
  \u0438\u0440\u043E\u0432\u0430\u0442\u044C. \u042D\u0442\u043E \u043A\u0440\u0438\
  \u0442\u0438\u0447\u0435\u0441\u043A\u0438 \u0432\u0430\u0436\u043D\u043E \u0434\
  \u043B\u044F\u2026"
lastmod: 2024-02-18 23:08:56.955913
model: gpt-4-0125-preview
summary: "\u0420\u0430\u0437\u0431\u043E\u0440 \u0434\u0430\u0442\u044B \u043E\u0437\
  \u043D\u0430\u0447\u0430\u0435\u0442 \u043F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\
  \u043E\u0432\u0430\u043D\u0438\u0435 \u0434\u0430\u0442\u044B \u0438\u0437 \u0442\
  \u0435\u043A\u0441\u0442\u043E\u0432\u043E\u0433\u043E \u0444\u043E\u0440\u043C\u0430\
  \u0442\u0430 \u0432 \u043E\u0431\u044A\u0435\u043A\u0442 \u0434\u0430\u0442\u044B\
  , \u043A\u043E\u0442\u043E\u0440\u044B\u0439 \u043F\u0440\u043E\u0433\u0440\u0430\
  \u043C\u043C\u0430 \u043C\u043E\u0436\u0435\u0442 \u043F\u043E\u043D\u0438\u043C\
  \u0430\u0442\u044C \u0438 \u043C\u0430\u043D\u0438\u043F\u0443\u043B\u0438\u0440\
  \u043E\u0432\u0430\u0442\u044C. \u042D\u0442\u043E \u043A\u0440\u0438\u0442\u0438\
  \u0447\u0435\u0441\u043A\u0438 \u0432\u0430\u0436\u043D\u043E \u0434\u043B\u044F\
  \u2026"
title: "\u0410\u043D\u0430\u043B\u0438\u0437 \u0434\u0430\u0442\u044B \u0438\u0437\
  \ \u0441\u0442\u0440\u043E\u043A\u0438"
---

{{< edit_this_page >}}

## Что и Почему?
Разбор даты означает преобразование даты из текстового формата в объект даты, который программа может понимать и манипулировать. Это критически важно для чтения данных из различных источников, таких как пользовательский ввод или файлы, позволяя программам обрабатывать и управлять датами и временем последовательно.

## Как это сделать:
В Kotlin вы можете анализировать даты с помощью класса `LocalDateTime` из пакета `java.time`. Давайте разберем строку в дату.

```kotlin
import java.time.LocalDateTime
import java.time.format.DateTimeFormatter

fun main() {
    val dateString = "2023-04-01T15:30:00"
    val formatter = DateTimeFormatter.ISO_LOCAL_DATE_TIME
    val parsedDate = LocalDateTime.parse(dateString, formatter)
    
    println(parsedDate)  // Пример вывода: 2023-04-01T15:30
}
```

## Подробнее
Kotlin не имеет собственной библиотеки даты и времени. Вместо этого он использует API `java.time`, представленный в Java 8, который заменил более старые, менее интуитивно понятные классы дат, такие как `java.util.Date`.

Большим плюсом `java.time` является то, что он принес неизменяемость и потокобезопасность в операции с датой-временем. До Java 8 за надежную работу с датами часто прибегали к сторонним библиотекам, таким как Joda-Time.

При анализе дат необходимо совпадение строки даты с правильным форматом. В противном случае вы столкнетесь с `DateTimeParseException`. Подход Kotlin основан на стандарте ISO 8601, но вы можете создавать собственные форматы с помощью `DateTimeFormatter` для разных шаблонов строк.

Альтернативы `LocalDateTime` включают `ZonedDateTime` для поддержки часовых поясов или `LocalDate` и `LocalTime` для раздельного анализа дат и времени. Гибкость Kotlin с API `java.time` гарантирует, что вы можете настроить разбор дат в соответствии с потребностями программы.

## Смотрите также
- Официальная документация Java `DateTimeFormatter`: [https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)
- Документация Kotlin о взаимодействии с Java: [https://kotlinlang.org/docs/java-interop.html](https://kotlinlang.org/docs/java-interop.html)
- Форматы дат и времени ISO 8601: [https://www.iso.org/iso-8601-date-and-time-format.html](https://www.iso.org/iso-8601-date-and-time-format.html)
