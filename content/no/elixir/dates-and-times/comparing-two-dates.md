---
date: 2024-01-20 17:32:32.952034-07:00
description: "Sammenligne to datoer er \xE5 vurdere deres forhold til hverandre -\
  \ f\xF8r, etter, eller samme dag. Programmerere trenger dette for \xE5 h\xE5ndtere\
  \ tidsavhengige\u2026"
lastmod: '2024-03-13T22:44:40.455850-06:00'
model: gpt-4-1106-preview
summary: "Sammenligne to datoer er \xE5 vurdere deres forhold til hverandre - f\xF8\
  r, etter, eller samme dag."
title: Sammenlikning av to datoer
weight: 27
---

## How to:
Elixir gjør det enkelt å sammenligne datoer ved hjelp av `Date.compare/2` funksjonen. Her er hvordan du gjør det:

```elixir
date1 = ~D[2023-04-01]
date2 = ~D[2023-05-01]

compared = Date.compare(date1, date2)

IO.puts "Result of comparison: #{compared}"
```

Kjører du dette, får du:
```
Result of comparison: :lt
```
Det betyr at `date1` er mindre enn (før) `date2`.

## Deep Dive
I Elixir, som ble utviklet av José Valim og først utgitt i 2011, håndterer `Date` modulen dato-relaterte funksjoner. `Date.compare/2` er foretrukket fordi det er innebygd og unngår den manuelle sammenligningen av år, måneder, og dager. Den returnerer `:eq`, `:lt`, eller `:gt` for henholdsvis likhet, mindre enn, eller større enn. 

Tidligere kunne du brukt tredjepartsbiblioteker som Timex for lignende funksjonalitet, men Elixirs standardbibliotek har modnet og dekker nå disse behovene godt. Implementasjonsmessig baserer Elixir seg på Erlang/OTP, en plattform kjent for sin styrke med tid og konkurranse.

## See Also
- Elixir `Date` modulen: https://hexdocs.pm/elixir/Date.html
- Erlang/OTP dokumentasjon: https://www.erlang.org/doc
- Timex biblioteket (for historisk sammenligning): https://hexdocs.pm/timex/readme.html
