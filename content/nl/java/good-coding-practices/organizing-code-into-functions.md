---
title:                "Code organiseren in functies"
aliases:
- /nl/java/organizing-code-into-functions/
date:                  2024-01-28T22:02:56.471306-07:00
model:                 gpt-4-0125-preview
simple_title:         "Code organiseren in functies"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/java/organizing-code-into-functions.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Code organiseren in functies betekent het opdelen van het beest dat een programma is in beheersbare delen, elk met een duidelijke taak. Programmeurs doen dit om code leesbaar, herbruikbaar en onderhoudbaar te maken.

## Hoe:
Hier is een klassiek voorbeeld - een functie om de faculteit van een getal te berekenen.

```java
public class MathUtils {

    public static void main(String[] args) {
        int number = 5;
        int result = factorial(number);
        System.out.println("Faculteit van " + number + " is: " + result);
    }
    
    public static int factorial(int n) {
        if (n <= 1) {
            return 1;
        }
        return n * factorial(n - 1);
    }
}
```

Uitvoer zou zijn:
```
Faculteit van 5 is: 120
```

## Diepgaand
Voordat functies een ding waren, werd code in monolithische blokken gepropt, waardoor debuggen leek op het vinden van een naald in een hooiberg. Nu helpt het inkapselen van functionaliteit in functies om snel problemen te isoleren. Alternatieven omvatten lambda-expressies in Java of methoden in objectgeoriënteerd programmeren, beide dienen vergelijkbare doeleinden. Wanneer je een functie schrijft, onthoud dan: (1) Elke functie moet één enkele verantwoordelijkheid hebben en (2) de naam van de functie moet duidelijk haar doel beschrijven.

## Zie Ook
Voor meer over het organiseren van code:
- Clean Code van Robert C. Martin
- Refactoring: Het verbeteren van het ontwerp van bestaande code door Martin Fowler
- [Oracle Java documentatie over het definiëren van methoden](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html)
