---
aliases:
- /uk/java/converting-a-string-to-lower-case/
date: 2024-01-20 17:38:26.274309-07:00
description: "Converting a string to lower case means changing all the uppercase letters\
  \ within a string to their lowercase equivalents. Programmers do it for\u2026"
lastmod: 2024-02-18 23:09:00.097039
model: gpt-4-1106-preview
summary: "Converting a string to lower case means changing all the uppercase letters\
  \ within a string to their lowercase equivalents. Programmers do it for\u2026"
title: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F \u0440\
  \u044F\u0434\u043A\u0430 \u0443 \u043D\u0438\u0436\u043D\u0456\u0439 \u0440\u0435\
  \u0433\u0456\u0441\u0442\u0440"
---

{{< edit_this_page >}}

## What & Why? (Що і Чому?)

Converting a string to lower case means changing all the uppercase letters within a string to their lowercase equivalents. Programmers do it for consistency, especially when comparing strings, ignoring case differences.

## How to: (Як це зробити:)

Use `toLowerCase()` method:

```java
public class LowerCaseExample {
    public static void main(String[] args) {
        String original = "Hello, Друзі!";
        String lowerCased = original.toLowerCase();
        System.out.println(lowerCased);
    }
}
```

Output:
```
hello, друзі!
```

## Deep Dive (Поглиблений розбір)

Historically, converting strings to lower case helped normalize data, avoiding mismatches due to case differences. Alternatives include using regular expressions or manually mapping characters, but `toLowerCase()` is built-in and robust. It considers locale: `String.toLowerCase(Locale locale)`. With this, you can specify how conversion behaves with locale-specific characters.

## See Also (Дивіться також)

- Oracle Java Documentation: [String.toLowerCase()](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#toLowerCase())
- Tutorial on Java Strings and locales: [Working with Strings](https://docs.oracle.com/javase/tutorial/i18n/text/string.html)
- Explore the Locale class: [Locale](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)
