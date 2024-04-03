---
date: 2024-01-20 17:45:59.607635-07:00
description: "\u0412\u0438\u0442\u044F\u0433\u0443\u0432\u0430\u043D\u043D\u044F \u043F\
  \u0456\u0434\u0440\u044F\u0434\u043A\u0456\u0432 \u0443 Java - \u0446\u0435 \u0441\
  \u043F\u043E\u0441\u0456\u0431 \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F\
  \ \u0447\u0430\u0441\u0442\u0438\u043D\u0438 \u0437 \u0440\u044F\u0434\u043A\u0430\
  . \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0440\u043E\
  \u0431\u043B\u044F\u0442\u044C \u0446\u0435, \u0449\u043E\u0431 \u043E\u0431\u0440\
  \u043E\u0431\u0438\u0442\u0438 \u0430\u0431\u043E \u0432\u0438\u043A\u043E\u0440\
  \u0438\u0441\u0442\u043E\u0432\u0443\u0432\u0430\u0442\u0438 \u043A\u043E\u043D\u043A\
  \u0440\u0435\u0442\u043D\u0456 \u0434\u0430\u043D\u0456 \u0437 \u0431\u0456\u043B\
  \u044C\u0448\u043E\u0433\u043E\u2026"
lastmod: '2024-03-13T22:44:49.062403-06:00'
model: gpt-4-1106-preview
summary: "\u0412\u0438\u0442\u044F\u0433\u0443\u0432\u0430\u043D\u043D\u044F \u043F\
  \u0456\u0434\u0440\u044F\u0434\u043A\u0456\u0432 \u0443 Java - \u0446\u0435 \u0441\
  \u043F\u043E\u0441\u0456\u0431 \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F\
  \ \u0447\u0430\u0441\u0442\u0438\u043D\u0438 \u0437 \u0440\u044F\u0434\u043A\u0430\
  ."
title: "\u0412\u0438\u0434\u0456\u043B\u0435\u043D\u043D\u044F \u043F\u0456\u0434\u0440\
  \u044F\u0434\u043A\u0456\u0432"
weight: 6
---

## Як це зробити:
```java
public class SubstringExample {
    public static void main(String[] args) {
        String fullString = "Привіт, світе!";
        String partOfString = fullString.substring(8, 13); // Витягує "світе"
        
        System.out.println("Повний рядок: " + fullString);
        System.out.println("Підрядок: " + partOfString);
    }
}

/*
Вивід:
Повний рядок: Привіт, світе!
Підрядок: світе
*/
```
Використовуйте метод `.substring()` для отримання частини рядка. Передайте індекс початку і кінця, щоб обмежити витягування.

## Поглиблений огляд:
В Java витягнення підрядків стало зазвичай завдяки `String` класу. З часів Java 1, ця можливість допомагає оптимізувати обробку текстів. Останні версії Java управляють рядками ефективніше, що зменшує пам'ять та прискорює доступ.

Альтернативами є методи `split()` або регулярні вирази (`Pattern` і `Matcher` класи), кожен із своїм використанням. Застосування `substring()` краще для простого і точного витягування певних сегментів тексту.

Реалізаційно, до Java 7, `substring()` створював новий рядок зі спільним масивом символів - економія пам'яті. Але з Java 7, `substring()` створює новий масив символів для кожного нового рядка, ліквідуючи залежність від оригінального рядка та потенційні витоки пам'яті.

## Дивіться також:
- [String (Java Platform SE 8)](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)
- [Class Pattern (Java Platform SE 8)](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)
- [Class Matcher (Java Platform SE 8)](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Matcher.html)
- [Effective Java (Third Edition) by Joshua Bloch](https://www.pearson.com/us/higher-education/program/Bloch-Effective-Java-3rd-Edition/PGM334830.html) - розділ про керування рядками для глибшого розуміння.
