---
title:                "Об'єднання рядків"
date:                  2024-01-20T17:35:10.967983-07:00
model:                 gpt-4-1106-preview
simple_title:         "Об'єднання рядків"
programming_language: "Java"
category:             "Java"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/java/concatenating-strings.md"
---

{{< edit_this_page >}}

## What & Why? (Що та Чому?)
String concatenation is the process of linking strings together. Programmers use it to combine text, like creating sentences dynamically in a program or generating complex formats.

## How to: (Як це зробити:)
```java
public class StringConcatenationExample {
    public static void main(String[] args) {
        String greeting = "Привіт";
        String who = "Світ";
        String exclamation = "!";
        
        String sentence = greeting + ", " + who + exclamation;
        System.out.println(sentence); // Вивід: Привіт, Світ!
        
        // Alternatively, using StringBuilder for better performance with many concatenations.
        StringBuilder sb = new StringBuilder();
        sb.append(greeting).append(", ").append(who).append(exclamation);
        System.out.println(sb.toString()); // Вивід: Привіт, Світ!
    }
}
```

## Deep Dive (Поглиблений Розгляд):
Originally, strings in Java were concatenated using `StringBuilder` or `StringBuffer` for thread-safe operations. These classes provide methods to append strings efficiently. Directly using the `+` operator for string concatenation is actually converted by the Java compiler to a `StringBuilder` operation. 

Why care about alternatives? Concatenating with `+` is fine for a few strings, but for many, it's less efficient. Each concatenation creates a new `String` object because strings are immutable in Java. `StringBuilder` is more memory-efficient for multiple concatenations and should be used in loops or when building large strings.

From a performance viewpoint for complex operations, `String.format()` and `MessageFormat` offer ways to create formatted strings, which internally also optimize string creation.

Java's history has shown continuous improvements in string handling, and JDK updates often include optimizations for these operations.

## See Also (Дивіться також):
- [Oracle Docs on Strings](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html)
- [StringBuilder JavaDoc](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/StringBuilder.html)
- [Effective Java by Joshua Bloch](https://www.oreilly.com/library/view/effective-java/9780134686097/) - See the section on strings and their performance.
- [Java Performance Tuning Guide](http://java-performance.info/) - Go here for in-depth performance tuning with Java strings.