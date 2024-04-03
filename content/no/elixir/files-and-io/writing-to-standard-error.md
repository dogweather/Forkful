---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:58.225684-07:00
description: "\xC5 skrive til standardfeil (stderr) i Elixir er en metode for \xE5\
  \ dirigere feilmeldinger og diagnostikk separat fra hovedutdataen (stdout). Programmerere\u2026"
lastmod: '2024-03-13T22:44:40.459830-06:00'
model: gpt-4-0125-preview
summary: "\xC5 skrive til standardfeil (stderr) i Elixir er en metode for \xE5 dirigere\
  \ feilmeldinger og diagnostikk separat fra hovedutdataen (stdout)."
title: Skriving til standardfeil
weight: 25
---

## Hvordan gjøre det:
I Elixir kan du bruke funksjoner i `IO`-modulen som `IO.puts/2` og `IO.warn/2` for å skrive meldinger til standardfeil:

```elixir
# Skrive en enkel melding til stderr
IO.puts(:stderr, "Feil: Noe gikk galt!")

# Bruke IO.warn, som er mer semantisk for advarsler/feil
IO.warn("Advarsel: Du er i ferd med å overskride grensen!")
```

Eksempel på utdata i terminalen for `IO.puts/2`:
```
Feil: Noe gikk galt!
```

For `IO.warn/2`, vil utdataen være lignende, men `IO.warn/2` er spesifikt designet for advarsler og kan inkludere ekstra formatering eller oppførsel i fremtidige Elixir-versjoner.

**Bruke tredjepartsbiblioteker**

Selv om Elixirs standardbibliotek vanligvis er tilstrekkelig for håndtering av standardfeilutdata, kan du finne biblioteker som `Logger` nyttige for mer komplekse applikasjoner eller for å konfigurere forskjellige loggnivåer og utdata.

Eksempel på bruk av `Logger` for å utgi en feilmelding:

```elixir
require Logger

# Konfigurer Logger for å utgi til stderr
Logger.configure_backend(:console, device: :stderr)

# Skrive en feilmelding
Logger.error("Feil: Klarte ikke å koble til databasen.")
```

Denne oppsettet dirigerer `Logger`'s utdata spesifikt til stderr, noe som er nyttig for å skille loggføring av feil fra standard loggmeldinger.
