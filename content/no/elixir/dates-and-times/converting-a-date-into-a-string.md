---
aliases:
- /no/elixir/converting-a-date-into-a-string/
date: 2024-01-20 17:36:09.563584-07:00
description: "Dato til streng-konvertering tar en dato og gj\xF8r den om til en tekstbasert\
  \ representasjon. Dette gj\xF8r det enklere \xE5 vise datoen for mennesker eller\
  \ \xE5\u2026"
lastmod: 2024-02-18 23:08:53.615896
model: gpt-4-1106-preview
summary: "Dato til streng-konvertering tar en dato og gj\xF8r den om til en tekstbasert\
  \ representasjon. Dette gj\xF8r det enklere \xE5 vise datoen for mennesker eller\
  \ \xE5\u2026"
title: Konvertere en dato til en streng
---

{{< edit_this_page >}}

## What & Why?
Dato til streng-konvertering tar en dato og gjør den om til en tekstbasert representasjon. Dette gjør det enklere å vise datoen for mennesker eller å lagre den i et tekstformat for systemintegrasjoner.

## How to:
Elixir håndterer datoer med en innebygd modul kalt `DateTime`. For å konvertere en dato til en streng, bruker vi `DateTime.to_string/1`:

```elixir
date = ~N[2023-09-17 14:30:00]
string_date = DateTime.to_string(date)
IO.puts(string_date)
```

Output:
```
"2023-09-17 14:30:00"
```

Du kan også bruke `Date.to_string/1` hvis du kun trenger datodelen:

```elixir
date = ~D[2023-09-17]
string_date = Date.to_string(date)
IO.puts(string_date)
```

Output:
```
"2023-09-17"
```

## Deep Dive
I historisk perspektiv har datoformat konverteringer vært viktig for å standardisere kommunikasjon mellom systemer, spesielt før standardiseringen av ISO 8601. Elixir bruker ISO 8601 som standard format for å representere dato og tid som tekst. Dette formatet er klart, entydig og lett å sortere.

Alternativer for konvertering inkluderer bruk av `Timex` biblioteket, som tilbyr mer fleksibilitet med formatering og tidssoner. `Cldr` er et annet bibliotek som støtter multikulturell datumformatering.

Når det gjelder implementeringsdetaljer, benytter `DateTime.to_string/1` seg av kalendermodulen som standard kalender, men det er mulig å tilpasse med andre kalendertyper som støttes av Elixir.

## See Also
For videre lesning, sjekk ut følgende ressurser:
- [Elixir's DateTime documentation](https://hexdocs.pm/elixir/DateTime.html)
- [ISO 8601 Standard](https://www.iso.org/iso-8601-date-and-time-format.html)
- [Timex GitHub repository](https://github.com/bitwalker/timex)
- [Cldr GitHub repository](https://github.com/elixir-cldr/cldr)
