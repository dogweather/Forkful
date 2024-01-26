---
title:                "Znalezienie długości ciągu znaków"
date:                  2024-01-20T17:47:52.848987-07:00
model:                 gpt-4-1106-preview
simple_title:         "Znalezienie długości ciągu znaków"
programming_language: "Java"
category:             "Java"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/java/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
**Co i Dlaczego?**

Znalezienie długości ciągu znaków to po prostu sprawdzenie, ile znaków zawiera. Programiści robią to, by walidować dane wejściowe, ograniczać tekst, lub po prostu operować na fragmentach ciągów.

## How to:
**Jak to zrobić:**

W Javie znajdźmy długość ciągu znaków używając metody `length()` obiektu `String`.

```java
public class StringLengthExample {
    public static void main(String[] args) {
        String myString = "Witaj, świecie!";
        int length = myString.length();
        System.out.println("Długość ciągu to: " + length);
    }
}
```

Wynik:

```
Długość ciągu to: 15
```

## Deep Dive
**Dogłębna Analiza**

`String` w Javie jest obiektem, który przechowuje sekwencje znaków. Metoda `length()` zwraca długość ciągu jako typ `int`. Została wprowadzona w pierwszej wersji Javy i od tego czasu jest standardowym sposobem na uzyskanie tej informacji. Alternatyw nie ma zbyt wiele – możesz iterować po znakach, ale to tylko skomplikuje kod. Ciekawostką jest to, że `length()` zwraca liczbę jednostek kodowych w ciągu, co może być mylące przy użyciu niektórych znaków Unicode, które wymagają dwóch jednostek kodowych.

## See Also
**Zobacz Także**

- [Dokumentacja Oracle dla klasy String](https://docs.oracle.com/javase/10/docs/api/java/lang/String.html)
- [Tutorial Oracle o ciągach znaków](https://docs.oracle.com/javase/tutorial/java/data/strings.html)
- [Stack Overflow: Różnice między length() a length w Javie](https://stackoverflow.com/questions/1735110/difference-between-string-length-and-length)
