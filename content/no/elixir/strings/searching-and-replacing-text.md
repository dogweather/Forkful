---
date: 2024-01-20 17:57:47.894526-07:00
description: "S\xF8king og erstattning av tekst lar oss finne bestemte ord eller uttrykk\
  \ og bytte dem ut med noe annet. Programmerere gj\xF8r dette for \xE5 oppdatere\
  \ kode,\u2026"
lastmod: '2024-03-13T22:44:40.428948-06:00'
model: gpt-4-1106-preview
summary: "S\xF8king og erstattning av tekst lar oss finne bestemte ord eller uttrykk\
  \ og bytte dem ut med noe annet."
title: "S\xF8king og erstatting av tekst"
weight: 10
---

## Hvordan:
For å søke og erstatte tekst i Elixir, bruker vi `String.replace/4` funksjonen. Her er et enkelt eksempel:

```elixir
original_tekst = "Hallo verden. Elixir er gøy. Hallo igjen!"
ny_tekst = String.replace(original_tekst, "Hallo", "Hei")
IO.puts ny_tekst
# Output:
# Hei verden. Elixir er gøy. Hei igjen!
```

Du kan også bruke regulære uttrykk for å identifisere mønstre:

```elixir
regex_tekst = "Epler 10, Bananer 20"
ny_regex_tekst = String.replace(regex_tekst, ~r/\d+/, fn _ -> "mange" end)
IO.puts ny_regex_tekst
# Output:
# Epler mange, Bananer mange
```

## Deep Dive
Søking og erstatning går langt tilbake og er en grunnleggende funksjon i tekstbehandling og programmering. I Elixir gjøres det enkelt og kraftfullt, med støtte for regulære uttrykk gjennom Erlang's `:re` modul, som Elixir tar i bruk.

Andre språk har lignende funksjoner, som `str.replace()` i Python eller `String.prototype.replace()` i JavaScript. I kontrast til noen språk som implementerer regulære uttrykk innad, bruker Elixir Erlang's implementasjon, som sikrer høy ytelse og stabilitet.

Når det gjelder implementasjonsdetaljer, håndterer `String.replace/4` funksjonen i Elixir både global og delvis erstatning. Den tar en valgfri fjerde parameter for å spesifisere blant annet antall erstatninger.

## Se Også
- Elixir's offisielle dokumentasjon for [String modulen](https://hexdocs.pm/elixir/String.html)
- Erlang's dokumentasjon om [Regular Expressions](http://erlang.org/doc/man/re.html)
- Et innføringskurs i regulære uttrykk: [RegexOne](https://regexone.com/)
