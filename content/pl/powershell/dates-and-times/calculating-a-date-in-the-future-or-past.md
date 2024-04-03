---
date: 2024-01-20 17:31:55.983163-07:00
description: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci to\
  \ spos\xF3b na ustalenie daty, kt\xF3ra jest okre\u015Blon\u0105 liczb\u0119 dni,\
  \ miesi\u0119cy, czy lat od daty wyj\u015Bciowej.\u2026"
lastmod: '2024-03-13T22:44:35.643398-06:00'
model: gpt-4-1106-preview
summary: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci to spos\xF3\
  b na ustalenie daty, kt\xF3ra jest okre\u015Blon\u0105 liczb\u0119 dni, miesi\u0119\
  cy, czy lat od daty wyj\u015Bciowej."
title: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci"
weight: 26
---

## Jak to zrobić:
```PowerShell
# Obliczanie daty 10 dni w przyszłości
$dzis = Get-Date
$przyszlosc = $dzis.AddDays(10)
"Data za 10 dni to: $przyszlosc"

# Obliczanie daty 5 dni w przeszłości
$przeszlosc = $dzis.AddDays(-5)
"Data sprzed 5 dni to: $przeszlosc"

# Przykładowe wyjście
Data za 10 dni to: czwartek, 10 lutego 2023 23:05:49
Data sprzed 5 dni to: sobota, 26 stycznia 2023 23:05:49
```

## Deep Dive
W przeszłości do obliczania dat używano różnych systemów i narzędzi – od kalendarzy papierowych po proste programy komputerowe. W PowerShellu obliczanie dat jest proste dzięki wbudowanym funkcjom, jak np. `AddDays()`, ale można też użyć `AddHours()`, `AddMonths()` i inne. Alternatywą jest także manualne dodawanie sekund, minut czy godzin do timestampów. Ważne jest zrozumienie stref czasowych i lokalnych ustawień czasu, by operacje na datach były poprawne w różnych środowiskach.

## Zobacz także
- [Dokumentacja PowerShell dla DateTime](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.1)
- [O strefach czasowych w .NET](https://docs.microsoft.com/en-us/dotnet/standard/datetime/choosing-between-datetime)
