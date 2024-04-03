---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:56:04.142385-07:00
description: "\u0412\u0438\u0434\u0430\u043B\u0435\u043D\u043D\u044F \u043B\u0430\u043F\
  \u043E\u043A \u0437 \u0440\u044F\u0434\u043A\u0430 \u0432 Dart \u043F\u0435\u0440\
  \u0435\u0434\u0431\u0430\u0447\u0430\u0454 \u0432\u0438\u043B\u0443\u0447\u0435\u043D\
  \u043D\u044F \u043F\u043E\u0434\u0432\u0456\u0439\u043D\u0438\u0445 (\") \u0430\u0431\
  \u043E \u043E\u0434\u0438\u043D\u0430\u0440\u043D\u0438\u0445 (') \u043B\u0430\u043F\
  \u043E\u043A \u043D\u0430 \u043F\u043E\u0447\u0430\u0442\u043A\u0443 \u0442\u0430\
  \ \u0432 \u043A\u0456\u043D\u0446\u0456 \u0440\u044F\u0434\u043A\u0430, \u0449\u043E\
  \ \u043A\u043E\u0440\u0438\u0441\u043D\u043E \u0434\u043B\u044F \u043E\u0447\u0438\
  \u0449\u0435\u043D\u043D\u044F \u0434\u0430\u043D\u0438\u0445 \u0430\u0431\u043E\
  \u2026"
lastmod: '2024-03-13T22:44:48.775549-06:00'
model: gpt-4-0125-preview
summary: "\u0412\u0438\u0434\u0430\u043B\u0435\u043D\u043D\u044F \u043B\u0430\u043F\
  \u043E\u043A \u0437 \u0440\u044F\u0434\u043A\u0430 \u0432 Dart \u043F\u0435\u0440\
  \u0435\u0434\u0431\u0430\u0447\u0430\u0454 \u0432\u0438\u043B\u0443\u0447\u0435\u043D\
  \u043D\u044F \u043F\u043E\u0434\u0432\u0456\u0439\u043D\u0438\u0445 (\") \u0430\u0431\
  \u043E \u043E\u0434\u0438\u043D\u0430\u0440\u043D\u0438\u0445 (') \u043B\u0430\u043F\
  \u043E\u043A \u043D\u0430 \u043F\u043E\u0447\u0430\u0442\u043A\u0443 \u0442\u0430\
  \ \u0432 \u043A\u0456\u043D\u0446\u0456 \u0440\u044F\u0434\u043A\u0430, \u0449\u043E\
  \ \u043A\u043E\u0440\u0438\u0441\u043D\u043E \u0434\u043B\u044F \u043E\u0447\u0438\
  \u0449\u0435\u043D\u043D\u044F \u0434\u0430\u043D\u0438\u0445 \u0430\u0431\u043E\
  \ \u043F\u0456\u0434\u0433\u043E\u0442\u043E\u0432\u043A\u0438 \u0440\u044F\u0434\
  \u043A\u0456\u0432 \u0434\u043B\u044F \u043F\u043E\u0434\u0430\u043B\u044C\u0448\
  \u043E\u0457 \u043E\u0431\u0440\u043E\u0431\u043A\u0438."
title: "\u0412\u0438\u0434\u0430\u043B\u0435\u043D\u043D\u044F \u043B\u0430\u043F\u043E\
  \u043A \u0437 \u0440\u044F\u0434\u043A\u0430"
weight: 9
---

## Як:
Dart надає прямолінійні способи видалення лапок з рядка, використовуючи вбудовані методи рядка без потреби в сторонніх бібліотеках.

### Приклад 1: Використання `replaceFirst` і `replaceAll`
Якщо ви працюєте з рядками, що починаються і закінчуються лапками, ви можете використовувати методи `replaceFirst` і `replaceAll` для їх видалення.

```dart
String quotedString = '"Привіт, світ!"';
String singleQuotedString = '\'Програмування Dart\'';

// Видалення подвійних лапок
String noDoubleQuotes = quotedString.replaceFirst('"', '').replaceAll('"', '');
print(noDoubleQuotes); // Вивід: Привіт, світ!

// Видалення одинарних лапок
String noSingleQuotes = singleQuotedString.replaceFirst('\'', '').replaceAll('\'', '');
print(noSingleQuotes); // Вивід: Програмування Dart
```

### Приклад 2: Використання `substring`
Цей метод корисний, коли ви впевнені, що лапки знаходяться саме на початку і в кінці рядка.

```dart
String quotedString = '"Розробка на Flutter"';
// Перевірте, чи починається і закінчується цими лапками, перш ніж видаляти, щоб уникнути помилок
if (quotedString.startsWith('"') && quotedString.endsWith('"')) {
  quotedString = quotedString.substring(1, quotedString.length - 1);
}
print(quotedString); // Вивід: Розробка на Flutter
```

### Приклад 3: Власний метод розширення
Для більшої повторюваності використання, особливо якщо ваш проєкт часто включає видалення лапок, розгляньте створення власного розширення для `String`.

```dart
extension UnquoteString on String {
  String unquote() {
    var str = this;
    if (str.startsWith('"') && str.endsWith('"') || str.startsWith('\'') && str.endsWith('\'')) {
      str = str.substring(1, str.length - 1);
    }
    return str;
  }
}

void main() {
  String doubleQuoted = '"Це Dart"';
  String singleQuoted = '\'Це чудово\'';
  print(doubleQuoted.unquote()); // Вивід: Це Dart
  print(singleQuoted.unquote()); // Вивід: Це чудово
}
```

Ці підходи допоможуть вам ефективно видаляти лапки з рядків у Dart, покращуючи ваші процеси обробки і підготовки даних.
