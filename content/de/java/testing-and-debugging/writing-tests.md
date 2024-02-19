---
aliases:
- /de/java/writing-tests/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:30:50.255026-07:00
description: "Das Schreiben von Tests in Java besteht darin, zu \xFCberpr\xFCfen,\
  \ ob Ihr Code sich unter verschiedenen Bedingungen wie erwartet verh\xE4lt. Programmierer\u2026"
lastmod: 2024-02-18 23:09:04.740546
model: gpt-4-0125-preview
summary: "Das Schreiben von Tests in Java besteht darin, zu \xFCberpr\xFCfen, ob Ihr\
  \ Code sich unter verschiedenen Bedingungen wie erwartet verh\xE4lt. Programmierer\u2026"
title: Tests Schreiben
---

{{< edit_this_page >}}

## Was & Warum?
Das Schreiben von Tests in Java besteht darin, zu überprüfen, ob Ihr Code sich unter verschiedenen Bedingungen wie erwartet verhält. Programmierer schreiben Tests, um Fehler zu vermeiden, die Funktionalität nach Änderungen korrekt zu halten und gute Software-Designprinzipien zu fördern.

## Wie:
Java-Entwickler verwenden hauptsächlich zwei Test-Frameworks: JUnit und TestNG. Hier konzentrieren wir uns auf JUnit, die beliebtere Wahl für das Schreiben von Tests aufgrund seiner Einfachheit und weit verbreiteten Akzeptanz.

### JUnit-Grundlagen

Um JUnit in Ihrem Maven-Projekt zu verwenden, fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.9.0</version>
    <scope>test</scope>
</dependency>
```

Ein grundlegender Test in JUnit sieht so aus:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

public class CalculatorTest {
    
    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3), "2 + 3 sollte 5 ergeben");
    }
}
```

Die Ausführung dieses Tests wird entweder bestehen, was darauf hinweist, dass die `add` Methode wie erwartet funktioniert, oder fehlschlagen, was eine Fehlermeldung anzeigt.

### Mocking mit Mockito

In realen Szenarien hängen Objekte oft von anderen Objekten ab. Mockito ist ein beliebtes Mocking-Framework, das beim Erstellen von Mock-Objekten zum Zweck des Testens hilft.

Fügen Sie Mockito Ihrem Maven-Projekt hinzu:

```xml
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>4.5.1</version>
    <scope>test</scope>
</dependency>
```

Ein einfacher Anwendungsfall mit Mockito:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;
import static org.mockito.Mockito.*;

public class UserServiceTest {

    @Test
    public void testGetUsername() {
        // Erstellen eines Mock UserRepository
        UserRepository mockRepository = mock(UserRepository.class);

        // Verhalten für Mock-Objekt definieren
        when(mockRepository.getUsername(1)).thenReturn("john_doe");

        UserService userService = new UserService(mockRepository);
        
        assertEquals("john_doe", userService.getUsername(1), "User-ID 1 sollte john_doe sein");
    }
}
```

Dieser Mock ermöglicht es uns, `UserService` zu testen, ohne ein tatsächliches `UserRepository` zu benötigen, wobei der Test sich auf die Logik innerhalb von `UserService` selbst konzentriert.
