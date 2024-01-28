---
title:                "Obsługa błędów"
date:                  2024-01-26T00:54:44.500120-07:00
model:                 gpt-4-1106-preview
simple_title:         "Obsługa błędów"
programming_language: "Java"
category:             "Java"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/java/handling-errors.md"
---

{{< edit_this_page >}}

## Co i dlaczego?

Obsługa błędów polega na pisaniu kodu, który przewiduje błędne sytuacje i radzi sobie z nimi. Programiści robią to, aby oprogramowanie było bardziej niezawodne, zapobiegając awariom i dziwnym zachowaniom.

## Jak to zrobić:

Java używa wyjątków do obsługi błędów. Ryzykowny kod umieszcza się w bloku `try` oraz przechwytuje wyjątki w bloku `catch`. Oto prosty przykład:

```java
public class PrzykladObslugiBledow {
    public static void main(String[] args) {
        try {
            int wynik = dzielenie(10, 0);
            System.out.println("Wynik to: " + wynik);
        } catch (ArithmeticException e) {
            System.out.println("Ups, nie można dzielić przez zero!");
        }
    }

    private static int dzielenie(int licznik, int mianownik) {
        return licznik / mianownik;
    }
}
```

Wynik:
```
Ups, nie można dzielić przez zero!
```

## Wnikliwe spojrzenie

Obsługa błędów w Javie ewoluowała. Na początku nie było wyjątków; programiści sprawdzali kody błędów. Następnie Java wprowadziła bloki try-catch, umożliwiające bardziej elegancką obsługę błędów.

Alternatywami dla tradycyjnych bloków `try-catch` są `try-with-resources` dla automatycznego zamykania zasobów i czystszego kodu, wprowadzone w Java 7.

Szczegóły implementacji mają znaczenie. Na przykład łapanie `Exception` lub `Throwable` jest zazwyczaj złą praktyką. Jest to zbyt ogólne i maskuje błędy, o których możesz nie wiedzieć. Trzymaj się konkretnych wyjątków.

## Zobacz również

- Oficjalne tutoriale Oracle Java na temat wyjątków: [https://docs.oracle.com/javase/tutorial/essential/exceptions/](https://docs.oracle.com/javase/tutorial/essential/exceptions/)
- Dokumentacja instrukcji `try-with-resources` w Javie: [https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html)
- Effective Java autorstwa Joshuy Blocha, dla najlepszych praktyk dotyczących wyjątków.
