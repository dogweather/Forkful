---
date: 2024-01-20 17:46:04.031025-07:00
description: "\u0429\u043E \u0442\u0430\u043A\u0435 \u043E\u0442\u0440\u0438\u043C\
  \u0430\u043D\u043D\u044F \u043F\u0456\u0434\u0440\u044F\u0434\u043A\u0456\u0432\
  \ \u0442\u0430 \u043D\u0430\u0432\u0456\u0449\u043E \u0446\u0435 \u043F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u0456\u0441\u0442\u0430\u043C? \u041E\u0442\u0440\u0438\
  \u043C\u0430\u043D\u043D\u044F \u043F\u0456\u0434\u0440\u044F\u0434\u043A\u0456\u0432\
  \ - \u0446\u0435 \u043C\u0435\u0442\u043E\u0434 \u0432\u0438\u0434\u0456\u043B\u0435\
  \u043D\u043D\u044F \u0447\u0430\u0441\u0442\u0438\u043D\u0438 \u0442\u0435\u043A\
  \u0441\u0442\u0443 \u0437 \u0440\u044F\u0434\u043A\u0430. \u041F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0446\u0435 \u0440\u043E\u0431\u043B\
  \u044F\u0442\u044C \u0434\u043B\u044F\u2026"
lastmod: '2024-03-13T22:44:49.201573-06:00'
model: gpt-4-1106-preview
summary: "\u0429\u043E \u0442\u0430\u043A\u0435 \u043E\u0442\u0440\u0438\u043C\u0430\
  \u043D\u043D\u044F \u043F\u0456\u0434\u0440\u044F\u0434\u043A\u0456\u0432 \u0442\
  \u0430 \u043D\u0430\u0432\u0456\u0449\u043E \u0446\u0435 \u043F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u0456\u0441\u0442\u0430\u043C."
title: "\u0412\u0438\u0434\u0456\u043B\u0435\u043D\u043D\u044F \u043F\u0456\u0434\u0440\
  \u044F\u0434\u043A\u0456\u0432"
weight: 6
---

## How to:
Ось як це робиться в Kotlin:

```Kotlin
fun main() {
    val text = "Привіт, як твої справи?"

    // Витягти підрядок від 7 до 19 символа
    val substring = text.substring(7, 20) // "як твої справи"
    println(substring)

    // Витягти підрядок з використанням діапазону
    val rangeSubstring = text.slice(7..19) // "як твої справи"
    println(rangeSubstring)
}
```

Вихідний результат обох методів однаковий:
```
як твої справи
як твої справи
```

## Deep Dive:
В повсякденному кодингу, отримання підрядків - фундаментальний інструмент. В Kotlin, метод `substring` з’явився з Java, оскільки Kotlin побудований так, щоб бути сумісним з Java бібліотеками. Альтернативно, можна використовувати `slice`, який приймає діапазони і забезпечує більш гнучкий спосіб виділення тексту.

Під капотом, ці методи оптимізовані для ефективної роботи з рядками, але варто пам’ятати про можливі `StringIndexOutOfBoundsException`, які можуть виникати при спробі доступу до неіснуючих індексів.

## See Also:
Для подальшого читання та навчання:
- [Kotlin documentation on substring](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/substring.html)
- [Oracle Java String documentation](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html) - адже розуміння Java допоможе з Kotlin
- [Kotlin Range Expressions](https://kotlinlang.org/docs/ranges.html)
