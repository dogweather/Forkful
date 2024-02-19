---
aliases:
- /pl/elixir/searching-and-replacing-text/
date: 2024-01-20 17:57:59.636146-07:00
description: "\"Co i Dlaczego?\" Wyszukiwanie i zamiana tekstu to szybka edycja, zmieniaj\u0105\
  ca fragmenty kodu czy tekstu. Programi\u015Bci robi\u0105 to, by poprawia\u0107\
  \ b\u0142\u0119dy,\u2026"
lastmod: 2024-02-18 23:08:49.291527
model: gpt-4-1106-preview
summary: "\"Co i Dlaczego?\" Wyszukiwanie i zamiana tekstu to szybka edycja, zmieniaj\u0105\
  ca fragmenty kodu czy tekstu. Programi\u015Bci robi\u0105 to, by poprawia\u0107\
  \ b\u0142\u0119dy,\u2026"
title: Wyszukiwanie i zamiana tekstu
---

{{< edit_this_page >}}

## What & Why?
"Co i Dlaczego?"

Wyszukiwanie i zamiana tekstu to szybka edycja, zmieniająca fragmenty kodu czy tekstu. Programiści robią to, by poprawiać błędy, aktualizować dane czy czyszczenie kodu.

## How to:
"Jak to zrobić?"

```elixir
# Podstawowa zamiana w ciągu znaków
original_text = "Witaj świecie, Elixir jest niesamowity!"
new_text = String.replace(original_text, "świecie", "Elixira")

IO.puts new_text
# Wynik: "Witaj Elixira, Elixir jest niesamowity!"

# Wyszukiwanie za pomocą wyrażeń regularnych
regex = ~r/jest (\w+)/
replacement = "to \\1 i wiele więcej"

IO.puts String.replace(original_text, regex, replacement)
# Wynik: "Witaj świecie, Elixir to niesamowity i wiele więcej"

# Zamiana wielu wzorców na raz
patterns = [{"Elixir", "Phoenix"}, {"jest", "to"}, {"niesamowity", "fantastyczny"}]

IO.puts Enum.reduce(patterns, original_text, fn {from, to}, acc -> 
  String.replace(acc, from, to) 
end)
# Wynik: "Witaj świecie, Phoenix to fantastyczny!"
```

## Deep Dive
"Głębsze spojrzenie"

Historia funkcji stringowych w Elixirze nawiązuje do systemu pattern matching w Erlangu. Wyszukiwanie i zamiana opierają się na potężnej składni wyrażeń regularnych, zapożyczonej z Perl'a. Alternatywą może być wykorzystanie funkcji związanych ze strumieniami (Streams), do przetwarzania dużych plików bez potrzeby ich wczytywania do pamięci. Sprawność implementacji tych funkcji w Elixirze pozwala na wydajne zarządzanie łańcuchami znaków, co jest kluczowe przy obsłudze protokołów sieciowych czy przetwarzaniu dużych zbiorów danych.

## See Also
"Zobacz też"

- Elixir Documentation on Strings: https://hexdocs.pm/elixir/String.html
- RegEx in Elixir (using `Regex` module): https://hexdocs.pm/elixir/Regex.html
- Chris McCord's "Metaprogramming Elixir" for patterns and matching: https://pragprog.com/titles/cmelixir/metaprogramming-elixir/
- Elixir School on Strings and Pattern Matching: https://elixirschool.com/en/lessons/basics/strings/
