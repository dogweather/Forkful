---
title:                "Scrivere test"
date:                  2024-02-03T19:30:52.141548-07:00
model:                 gpt-4-0125-preview
simple_title:         "Scrivere test"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/java/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa & Perché?
Scrivere test in Java consiste nel verificare che il proprio codice si comporti come previsto in varie condizioni. I programmatori scrivono test per prevenire bug, assicurare che la funzionalità rimanga corretta dopo modifiche e promuovere buoni principi di progettazione del software.

## Come fare:
Gli sviluppatori Java utilizzano principalmente due framework di test: JUnit e TestNG. Qui, ci concentreremo su JUnit, la scelta più popolare per scrivere test grazie alla sua semplicità e alla diffusa adozione.

### Fondamenti di JUnit

Per utilizzare JUnit nel tuo progetto Maven, aggiungi la seguente dipendenza al tuo `pom.xml`:

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.9.0</version>
    <scope>test</scope>
</dependency>
```

Un test di base in JUnit si presenta così:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

public class CalculatorTest {
    
    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3), "2 + 3 dovrebbe fare 5");
    }
}
```

Eseguendo questo test, il risultato sarà o il superamento, indicando che il metodo `add` funziona come previsto, o il fallimento, mostrando un messaggio di errore.

### Simulazione con Mockito

In scenari reali, gli oggetti spesso dipendono da altri oggetti. Mockito è un framework di simulazione popolare che aiuta nella creazione di oggetti fittizi ai fini del test.

Aggiungi Mockito al tuo progetto Maven:

```xml
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>4.5.1</version>
    <scope>test</scope>
</dependency>
```

Un semplice caso d'uso con Mockito:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;
import static org.mockito.Mockito.*;

public class UserServiceTest {

    @Test
    public void testGetUsername() {
        // Crea un UserRepository fittizio
        UserRepository mockRepository = mock(UserRepository.class);

        // Definisci il comportamento per l'oggetto fittizio
        when(mockRepository.getUsername(1)).thenReturn("john_doe");

        UserService userService = new UserService(mockRepository);
        
        assertEquals("john_doe", userService.getUsername(1), "L'ID utente 1 dovrebbe essere john_doe");
    }
}
```

Questo mock ci permette di testare `UserService` senza la necessità di un vero `UserRepository`, concentrando il test sulla logica all'interno di `UserService` stesso.
