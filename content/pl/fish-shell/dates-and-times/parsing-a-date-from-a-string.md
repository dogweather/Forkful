---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:25.591683-07:00
description: "Parsowanie daty ze stringa polega na ekstrahowaniu informacji o dacie\
  \ zakodowanej w ci\u0105gach znak\xF3w i konwersji jej na strukturyzowany format,\
  \ kt\xF3ry\u2026"
lastmod: '2024-03-13T22:44:35.851091-06:00'
model: gpt-4-0125-preview
summary: "Parsowanie daty ze stringa polega na ekstrahowaniu informacji o dacie zakodowanej\
  \ w ci\u0105gach znak\xF3w i konwersji jej na strukturyzowany format, kt\xF3ry \u015B\
  rodowiska programistyczne mog\u0105 rozpoznawa\u0107 i manipulowa\u0107."
title: "Analiza sk\u0142adniowa daty z \u0142a\u0144cucha znak\xF3w"
weight: 30
---

## Jak to zrobić:
W Fish Shell nie masz wbudowanych poleceń specjalnie zaprojektowanych do parsowania dat z ciągów znaków. Zamiast tego, polegasz na zewnętrznych narzędziach takich jak `date` (dostępne w Linux i macOS) lub wykorzystujesz popularne narzędzia stron trzecich takie jak `GNU date` do bardziej skomplikowanego parsowania. Oto jak się za to zabrać:

**Korzystając z `date` w Fish:**

Aby przeanalizować ciąg daty w formacie "RRRR-MM-DD", możesz użyć polecenia `date` z opcją `-d` (lub `--date` dla GNU date) po której następuje string. Opcja `+` jest używana do formatowania wyjścia.

```fish
set date_str "2023-04-01"
date -d $date_str +"%A, %d %B %Y"
# Wyjście: Sobota, 01 Kwiecień 2023
```

Dla systemu macOS (który wymaga innego formatu dla flag `-j` i `-f`):

```fish
set date_str "2023-04-01"
date -j -f "%Y-%m-%d" $date_str +"%A, %d %B %Y"
# Wyjście: Sobota, 01 Kwiecień 2023
```

**Korzystając z GNU `date` do skomplikowanego parsowania:**

GNU `date` jest bardziej elastyczne w zakresie formatów ciągów. Może automatycznie wykrywać wiele wspólnych formatów ciągów dat bez konieczności jawnego określania formatu wejściowego:

```fish
set complex_date_str "1 Kwiecień 2023 14:00"
date -d "$complex_date_str" '+%Y-%m-%d %H:%M:%S'
# Wyjście: 2023-04-01 14:00:00
```

Jednak, przy pracy z ciągami dat, które mogą nie być automatycznie rozpoznawane lub gdy potrzebna jest precyzyjna kontrola nad formatem wejściowym, jawne określenie formatu wejściowego z GNU `date` nie jest bezpośrednio obsługiwane. W takich przypadkach rozważ przetworzenie wcześniejsze ciągu lub użycie innego narzędzia zaprojektowanego do bardziej skomplikowanych rutyn parsowania dat.
