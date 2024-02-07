---
title:                "Łączenie łańcuchów znaków"
date:                  2024-01-20T17:35:49.050839-07:00
model:                 gpt-4-1106-preview
simple_title:         "Łączenie łańcuchów znaków"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/python/concatenating-strings.md"
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)

Łączenie ciągów znaków (stringów) to proces tworzenia jednego ciągu ze dwojga lub więcej. Programiści używają tej techniki do budowania komunikatów, danych i skryptów - to podstawy manipulowania tekstami.

## How to: (Jak to zrobić?)

Łączenie stringów w Pythonie możemy zrealizować na różne sposoby. Tutaj kilka przykładów:

```Python
# Przykład 1: operator +
powitanie = "Cześć, " + "jak się masz?"
print(powitanie)  # Wyjście: Cześć, jak się masz?

# Przykład 2: f-string
imie = "Olaf"
przywitanie = f"Witaj {imie}!"
print(przywitanie)  # Wyjście: Witaj Olaf!

# Przykład 3: metoda join()
lista_slow = ["Hej", "to", "ja"]
calosc = " ".join(lista_slow)
print(calosc)  # Wyjście: Hej to ja
```

## Deep Dive (Głębsze spojrzenie)

Kiedyś, w Pythonie 2, popularnym sposobem łączenia stringów była operacja `%` zwaną operatorem interpolacji. Przykład:

```Python
imie = "Karol"
powitanie = "Hej %s!" % imie
```

Jednak od Pythona 3.6+, f-stringi (literal string interpolation) stały się zalecanym sposobem formatowania ciągów. Szybkie, czytelne i mniej podatne na błąd.

Alternatywą może być metoda `format()`, która istnieje od Pythona 2.6+:

```Python
powitanie = "Cześć, {}!".format(imie)
```

Kwestią techniczną jest fakt, że ciągi znaków w Pythonie są niemutowalne, co oznacza, że każda operacja łączenia tworzy nowy ciąg, nie modyfikując istniejących. Dlatego, przy łączeniu dużej liczby stringów, `join()` jest wydajniejszy niż wielokrotne użycie `+`, ponieważ `+` w każdym kroku tworzy nowy string, co jest kosztowne przy dużych ilościach danych.

## See Also (Zobacz również)

- Dokumentacja Pythona na temat f-stringów: https://docs.python.org/3/reference/lexical_analysis.html#formatted-string-literals
- Dokumentacja metody `str.join()`: https://docs.python.org/3/library/stdtypes.html#str.join
- Dokumentacja metody `format()`: https://docs.python.org/3/library/stdtypes.html#str.format

Rozszerz swoją wiedzę o łączeniu łańcuchów znaków i wykorzystuj je z głową. Znajdziesz stosowne przykłady w dokumentacji Pythona, która jest świetnym zasobem dla każdego programisty.
