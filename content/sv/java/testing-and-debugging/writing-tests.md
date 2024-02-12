---
title:                "Skriva tester"
aliases:
- /sv/java/writing-tests/
date:                  2024-02-03T19:31:00.123405-07:00
model:                 gpt-4-0125-preview
simple_title:         "Skriva tester"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/java/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?
Att skriva tester i Java handlar om att verifiera att din kod beter sig som förväntat under olika förhållanden. Programmerare skriver tester för att förhindra buggar, säkerställa att funktionaliteten förblir korrekt efter ändringar och främja goda principer för mjukvarudesign.

## Hur:
Java-utvecklare använder främst två testramverk: JUnit och TestNG. Här kommer vi att fokusera på JUnit, det populärare valet för att skriva tester på grund av dess enkelhet och utbredda användning.

### JUnit-grunder

För att använda JUnit i ditt Maven-projekt, lägg till följande beroende i din `pom.xml`:

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.9.0</version>
    <scope>test</scope>
</dependency>
```

Ett grundläggande test i JUnit ser ut så här:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

public class CalculatorTest {
    
    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3), "2 + 3 bör bli 5");
    }
}
```

Utförandet av detta test kommer antingen att passera, vilket indikerar att `add`-metoden fungerar som förväntat, eller misslyckas, vilket visar ett felmeddelande.

### Mocking med Mockito

I verkliga scenarier är objekt ofta beroende av andra objekt. Mockito är ett populärt mockningsramverk som hjälper till att skapa mockobjekt i syfte att testa.

Lägg till Mockito i ditt Maven-projekt:

```xml
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>4.5.1</version>
    <scope>test</scope>
</dependency>
```

Ett enkelt användningsfall med Mockito:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;
import static org.mockito.Mockito.*;

public class UserServiceTest {

    @Test
    public void testGetUsername() {
        // Skapa en mock UserRepository
        UserRepository mockRepository = mock(UserRepository.class);

        // Definiera beteende för mockobjekt
        when(mockRepository.getUsername(1)).thenReturn("john_doe");

        UserService userService = new UserService(mockRepository);
        
        assertEquals("john_doe", userService.getUsername(1), "Användar-ID 1 bör vara john_doe");
    }
}
```

Denna mock gör att vi kan testa `UserService` utan att behöva en faktisk `UserRepository`, vilket fokuserar testet på logiken inom `UserService` självt.
