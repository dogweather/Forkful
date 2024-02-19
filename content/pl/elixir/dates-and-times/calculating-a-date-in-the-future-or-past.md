---
aliases:
- /pl/elixir/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:30:55.747152-07:00
description: "Co to jest i dlaczego? Obliczanie daty w przysz\u0142o\u015Bci albo\
  \ przesz\u0142o\u015Bci to ustalanie nowych dat na podstawie zadanej. Programi\u015B\
  ci robi\u0105 to dla organizacji\u2026"
lastmod: 2024-02-18 23:08:49.319584
model: gpt-4-1106-preview
summary: "Co to jest i dlaczego? Obliczanie daty w przysz\u0142o\u015Bci albo przesz\u0142\
  o\u015Bci to ustalanie nowych dat na podstawie zadanej. Programi\u015Bci robi\u0105\
  \ to dla organizacji\u2026"
title: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci"
---

{{< edit_this_page >}}

## What & Why?
Co to jest i dlaczego?

Obliczanie daty w przyszłości albo przeszłości to ustalanie nowych dat na podstawie zadanej. Programiści robią to dla organizacji wydarzeń, planowania zadań, przypomnień czy też wygaśnięcia sesji.

## How to:
Jak to zrobić:

```
# Dodawanie dni
date = ~D[2023-04-01]
future_date = Date.add(date, 10)
IO.puts(Date.to_string(future_date)) # 2023-04-11

# Odejmowanie dni
past_date = Date.add(date, -20)
IO.puts(Date.to_string(past_date)) # 2023-03-12
```

## Deep Dive:
Głębsze zanurzenie:

W Elixirze, moduł `Date` jest kluczowy do pracy z datami. Historia koncepcji operacji na datach sięga kalendarzy i potrzeby śledzenia czasu. Alternatywy do `Date.add` to użycie paczek zewnętrznych jak `Timex`, które dodają dodatkową funkcjonalność. Elixir używa kalendariów, by obsłużyć różne systemy datowania, a `Date.add` operuje w kontekście kalendarza Gregoriańskiego.

## See Also:
Zobacz także:

- [Elixir Documentation for Date](https://hexdocs.pm/elixir/Date.html)
- [Hex.pm package for Timex](https://hex.pm/packages/timex)
- [Elixir School: Dates and Times](https://elixirschool.com/en/lessons/basics/date-time/)
