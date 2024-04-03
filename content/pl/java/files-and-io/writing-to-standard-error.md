---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:33:52.084964-07:00
description: "Zapis do standardowego b\u0142\u0119du (stderr) polega na wyprowadzaniu\
  \ komunikat\xF3w o b\u0142\u0119dach i diagnostyki na konsol\u0119 lub terminal.\
  \ Programi\u015Bci robi\u0105 to, aby\u2026"
lastmod: '2024-03-13T22:44:35.294322-06:00'
model: gpt-4-0125-preview
summary: "Zapis do standardowego b\u0142\u0119du (stderr) polega na wyprowadzaniu\
  \ komunikat\xF3w o b\u0142\u0119dach i diagnostyki na konsol\u0119 lub terminal."
title: "Pisanie do standardowego b\u0142\u0119du"
weight: 25
---

## Jak to zrobić:


### Podstawowy zapis do stderr w Javie
Java oferuje prosty sposób na zapis do stderr za pomocą `System.err.print()` lub `System.err.println()`. Oto jak to zrobisz:

```java
public class StdErrExample {
    public static void main(String[] args) {
        try {
            int division = 10 / 0;
        } catch (ArithmeticException e) {
            System.err.println("Błąd: Nie można dzielić przez zero.");
        }
    }
}
```

Przykładowe wyjście:

```
Błąd: Nie można dzielić przez zero.
```

To bezpośrednio wydrukuje komunikat o błędzie do strumienia standardowego błędu.

### Użycie Loggera dla Zaawansowanego Obsługiwania Błędów
W aplikacjach wymagających bardziej zaawansowanego obsługiwania błędów i logowania, powszechne jest używanie biblioteki logowania jak SLF4J z Logbackiem lub Log4J2. Pozwala to na większą elastyczność w zarządzaniu wyjściem błędu, w tym przekierowanie do pliku, filtrowanie i formatowanie.

#### Przykład z Logbackiem
Najpierw, dodaj zależność do Logbacka do pliku `pom.xml` (Maven) lub `build.gradle` (Gradle). Dla Mavena:

```xml
<dependency>
    <groupId>ch.qos.logback</groupId>
    <artifactId>logback-classic</artifactId>
    <version>1.2.3</version>
</dependency>
```

Następnie możesz użyć poniższego kodu do logowania błędów:

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class LoggerExample {
    private static final Logger logger = LoggerFactory.getLogger(LoggerExample.class);
    
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            logger.error("Błąd: Nie można dzielić przez zero.", e);
        }
    }
}
```

To wydrukuje komunikat o błędzie wraz ze śladem stosu na konsolę lub do pliku, w zależności od konfiguracji Logbacka.

Używanie frameworków logowania jak Logback daje większą kontrolę nad obsługą błędów, ułatwiając zarządzanie dużymi aplikacjami i systemami.
