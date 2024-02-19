---
aliases:
- /uk/kotlin/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:31:45.050721-07:00
description: "\u0420\u043E\u0437\u0440\u0430\u0445\u0443\u043D\u043E\u043A \u0434\u0430\
  \u0442\u0438 \u0432 \u043C\u0430\u0439\u0431\u0443\u0442\u043D\u044C\u043E\u043C\
  \u0443 \u0447\u0438 \u043C\u0438\u043D\u0443\u043B\u043E\u043C\u0443 \u2014 \u0446\
  \u0435 \u043F\u0440\u043E\u0441\u0442\u043E \u0437\u043C\u0456\u0449\u0435\u043D\
  \u043D\u044F \u0432\u0456\u0434\u043B\u0456\u043A\u0443 \u0447\u0430\u0441\u0443\
  \ \u043D\u0430 \u043F\u0435\u0432\u043D\u0438\u0439 \u043F\u0435\u0440\u0456\u043E\
  \u0434. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0446\
  \u0435 \u0440\u043E\u0431\u043B\u044F\u0442\u044C \u0434\u043B\u044F \u043E\u0431\
  \u0440\u043E\u0431\u043A\u0438 \u043F\u043E\u0434\u0456\u0439, \u0440\u0435\u0437\
  \u0435\u0440\u0432\u0443\u0432\u0430\u043D\u043D\u044F,\u2026"
lastmod: 2024-02-18 23:09:00.290407
model: gpt-4-1106-preview
summary: "\u0420\u043E\u0437\u0440\u0430\u0445\u0443\u043D\u043E\u043A \u0434\u0430\
  \u0442\u0438 \u0432 \u043C\u0430\u0439\u0431\u0443\u0442\u043D\u044C\u043E\u043C\
  \u0443 \u0447\u0438 \u043C\u0438\u043D\u0443\u043B\u043E\u043C\u0443 \u2014 \u0446\
  \u0435 \u043F\u0440\u043E\u0441\u0442\u043E \u0437\u043C\u0456\u0449\u0435\u043D\
  \u043D\u044F \u0432\u0456\u0434\u043B\u0456\u043A\u0443 \u0447\u0430\u0441\u0443\
  \ \u043D\u0430 \u043F\u0435\u0432\u043D\u0438\u0439 \u043F\u0435\u0440\u0456\u043E\
  \u0434. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0446\
  \u0435 \u0440\u043E\u0431\u043B\u044F\u0442\u044C \u0434\u043B\u044F \u043E\u0431\
  \u0440\u043E\u0431\u043A\u0438 \u043F\u043E\u0434\u0456\u0439, \u0440\u0435\u0437\
  \u0435\u0440\u0432\u0443\u0432\u0430\u043D\u043D\u044F,\u2026"
title: "\u041E\u0431\u0447\u0438\u0441\u043B\u0435\u043D\u043D\u044F \u0434\u0430\u0442\
  \u0438 \u0443 \u043C\u0430\u0439\u0431\u0443\u0442\u043D\u044C\u043E\u043C\u0443\
  \ \u0430\u0431\u043E \u043C\u0438\u043D\u0443\u043B\u043E\u043C\u0443"
---

{{< edit_this_page >}}

## Що і чому?
Розрахунок дати в майбутньому чи минулому — це просто зміщення відліку часу на певний період. Програмісти це роблять для обробки подій, резервування, моніторингу чи прогнозування.

## Як робити:
В Kotlin ми використовуємо клас `LocalDate` з пакету `java.time`. Ось як це працює:

```Kotlin
import java.time.LocalDate
import java.time.temporal.ChronoUnit

fun main() {
    val today = LocalDate.now()
    val tenDaysLater = today.plusDays(10)
    val twoWeeksEarlier = today.minusWeeks(2)
  
    println("Сьогодні: $today")
    println("Через 10 днів: $tenDaysLater")
    println("Дві неділі тому: $twoWeeksEarlier")
}
```

Вам покажуть поточну дату, дату через 10 днів, і дату дві неділі назад.

## Поглиблено:
Раніше для роботи з датами програмісти використовували `java.util.Date` та `java.util.Calendar`. Однак, з Java 8 з'явився новий API для дати і часу - `java.time`, котрий і взяла за основу Kotlin. 

Ви також можете використовувати `plus` і `minus` з різними одиницями часу, як-от `ChronoUnit.DAYS` для днів чи `ChronoUnit.WEEKS` для тижнів. Це надає гнучкості роботі з часовими періодами.

Окрім того, кутлінівська бібліотека KotlinX.datetime додає додаткові функції для роботи з датою і часом, особливо корисні для cross-platform розробки.

## Також подивіться:
- [Документація по API java.time](https://docs.oracle.com/javase/8/docs/api/java/time/package-summary.html)
- [KotlinX.datetime бібліотека](https://github.com/Kotlin/kotlinx-datetime)
- [Путівник по міграції з java.util.Date на java.time](https://www.baeldung.com/migrating-to-java-8-date-time-api)
