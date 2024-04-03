---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:43.918618-07:00
description: "Regul\xE6re uttrykk (regex) er sekvenser av tegn som former et s\xF8\
  kem\xF8nster, prim\xE6rt brukt for strengs\xF8king og manipulasjon. Programmerere\
  \ utnytter regex i\u2026"
lastmod: '2024-03-13T22:44:41.006436-06:00'
model: gpt-4-0125-preview
summary: "Regul\xE6re uttrykk (regex) er sekvenser av tegn som former et s\xF8kem\xF8\
  nster, prim\xE6rt brukt for strengs\xF8king og manipulasjon."
title: "Bruke regul\xE6re uttrykk"
weight: 11
---

## Hvordan:
I PowerShell kan du bruke operatørene `-match`, `-replace` og `-split`, blant andre, for å utføre handlinger med regulære uttrykk. La oss utforske noen eksempler:

### Bruke `-match` for å sjekke om en streng matcher et mønster
Denne operatøren returnerer `$true` hvis mønsteret er funnet innen strengen, og `$false` ellers.

```powershell
"hello world" -match "\w+orld"
# Utdata: True
```

### Ekstrahere treff
Du kan trekke ut den treffende verdien ved å aksessere den automatiske variabelen `$matches`.

```powershell
if ("I have 100 apples" -match "\d+") {
    "Nummer funnet: " + $matches[0]
}
# Utdata: Nummer funnet: 100
```

### Bruke `-replace` for erstatninger
Operatøren `-replace` erstatter alle forekomster av et mønster med en spesifisert erstatningstekst.

```powershell
"foo bar baz" -replace "ba[rz]", "qux"
# Utdata: foo qux qux
```

### Dele strenger med `-split`
Del en streng inn i et array av delstrenger basert på et regex-mønster.

```powershell
"The quick-brown_fox jumps" -split "[-_ ]"
# Utdata: The quick brown fox jumps
```

### Avansert Mønstergjenkjenning
PowerShell støtter også mer komplekse regex-operasjoner via `[regex]`-klassen, som gir deg tilgang til metoder som `Matches()`, `Replace()`, og `Split()`.

```powershell
[regex]::Matches("June 24, August 9, Dec 12", "\b[A-Za-z]+\b").Value
# Utdata: June August Dec

[regex]::Replace("100,000", "\B(?=(?:\d{3})+(?!\d))", ",")
# Utdata: 100,000

[regex]::Split("one,two;three four", ",|;| ")
# Utdata: one two three four
```

Disse eksemplene viser kraften og allsidigheten til regulære uttrykk i PowerShell for datamanipulasjon og mønstergjenkjenning. Ved å utnytte regex, kan programmerere utføre kompleks tekstbehandling effektivt.
