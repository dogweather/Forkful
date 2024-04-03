---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:12:36.641748-07:00
description: "Assosiative tabeller, ogs\xE5 kjent som hashtabeller eller ordb\xF8\
  ker i PowerShell, lar deg lagre data i n\xF8kkel-verdipar, noe som gj\xF8r datahenting\
  \ enkel og\u2026"
lastmod: '2024-03-13T22:44:41.009142-06:00'
model: gpt-4-0125-preview
summary: "Assosiative tabeller, ogs\xE5 kjent som hashtabeller eller ordb\xF8ker i\
  \ PowerShell, lar deg lagre data i n\xF8kkel-verdipar, noe som gj\xF8r datahenting\
  \ enkel og effektiv."
title: Bruke associative tabeller
weight: 15
---

## Hvordan:
Å opprette og bruke assosiative tabeller i PowerShell er ganske rett frem. Slik gjør du magien:

**Opprette en assosiativ tabell:**

```PowerShell
$minAssosiativeTabell = @{}
$minAssosiativeTabell["navn"] = "Alex"
$minAssosiativeTabell["alder"] = 25
$minAssosiativeTabell["jobb"] = "Ingeniør"
```

Denne kodesnutten oppretter en assosiativ tabell med tre nøkkel-verdipar.

**Tilgang verdier:**

For å hente en verdi, referer til nøkkelen dens:

```PowerShell
Write-Output $minAssosiativeTabell["navn"]
```

**Eksempel på utdata:**

```
Alex
```

**Legge til eller endre data:**

Bare bruk nøkkelen for å legge til et nytt par eller modifisere et eksisterende:

```PowerShell
$minAssosiativeTabell["sted"] = "New York" # Legger til et nytt nøkkel-verdipar
$minAssosiativeTabell["jobb"] = "Senioringeniør" # Modifiserer et eksisterende par
```

**Iterere over en assosiativ tabell:**

Loop gjennom nøkler og verdier slik:

```PowerShell
foreach ($nøkkel in $minAssosiativeTabell.Keys) {
  $verdi = $minAssosiativeTabell[$nøkkel]
  Write-Output "$nøkkel : $verdi"
}
```

**Eksempel på utdata:**

```
navn : Alex
alder : 25
jobb : Senioringeniør
sted : New York
```

## Dypdykk
Konseptet med assosiative tabeller er vanlig på tvers av mange programmeringsspråk, vanligvis kalt en ordbok, map, eller hashtabell avhengig av språket. I PowerShell implementeres assosiative tabeller som hashtabeller, som er ganske effektive for å slå opp nøkler, lagre data og vedlikeholde en samling av unike nøkler.

Historisk sett gir assosiative tabeller et middel for å håndtere samlinger av objekter der hvert element kan hentes raskt uten å iterere gjennom hele samlingen, ved hjelp av nøkkelen dens. Effektiviteten av datahenting og modifikasjon i assosiative tabeller gjør dem til et foretrukket valg for forskjellige oppgaver. De har imidlertid begrensninger, som å opprettholde rekkefølge, der ordnede ordbøker eller egendefinerte objekter kan være et bedre alternativ.

Til tross for deres begrensninger, er assosiative tabeller/hashtabeller i PowerShell utrolig fleksible og et kraftig verktøy for scriptskriving. De tillater dynamisk datalagring og er spesielt nyttige i konfigurasjoner, datamanipulasjon, og hvor som helst en strukturert dataformat er nødvendig uten overhodet av en formell klassedefinisjon. Bare husk, mens assosiative tabeller er perfekte for nøkkelbasert henting, hvis oppgaven din innebærer komplekse datastrukturer eller krever å opprettholde en spesifikk rekkefølge, vil du kanskje utforske andre datatyper eller egendefinerte objekter innen PowerShell.
