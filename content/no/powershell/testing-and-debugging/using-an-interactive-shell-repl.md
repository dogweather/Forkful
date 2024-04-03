---
date: 2024-01-26 04:16:52.245545-07:00
description: "Det interaktive skallet, eller Read-Eval-Print Loop (REPL), lar deg\
  \ skrive PowerShell-kommandoer og f\xE5 umiddelbar tilbakemelding. Programmerere\
  \ bruker det\u2026"
lastmod: '2024-03-13T22:44:41.019475-06:00'
model: gpt-4-0125-preview
summary: "Det interaktive skallet, eller Read-Eval-Print Loop (REPL), lar deg skrive\
  \ PowerShell-kommandoer og f\xE5 umiddelbar tilbakemelding."
title: Bruke et interaktivt skall (REPL)
weight: 34
---

## Hvordan:
Start PowerShell, og du er i REPL. Prøv `Get-Date` Cmdlet:

```PowerShell
PS > Get-Date
```

Du burde se utskriften av gjeldende dato og klokkeslett:

```PowerShell
Onsdag, 31. mars 2023 12:34:56 PM
```

Nå kan du kjede kommandoer. La oss sortere prosesser etter minnebruk:

```PowerShell
PS > Get-Process | Sort-Object WS -Descending | Select-Object -First 5
```

Dette gir ut de fem øverste prosessene etter størrelse på arbeidssett (minnebruk).

## Dypdykk
PowerShell sin REPL har sine røtter i Unix-skallet og andre dynamiske språkskall som Python sitt. Det er et enkeltbruker, interaktivt kommando-utførelsesmiljø. I motsetning til et kompilert språk hvor du skriver hele applikasjoner og deretter kompilerer, lar et REPL-miljø deg skrive og kjøre kode en linje av gangen. PowerShell støtter også skriptkjøring for større oppgaver.

Alternativer for Windows inkluderer Kommandoprompt eller andre språkspesifikke REPL-er som IPython. I Unix/Linux-verdenen tjener skall som bash eller zsh en lignende funksjon.

PowerShell sin implementasjon bruker en vertsapplikasjon for å kjøre skallet. Selv om PowerShell.exe i Windows er mest vanlig, kan andre som det integrerte skriptmiljøet (ISE) eller Visual Studio Codes integrerte terminal også tjene som vert.

## Se også
- [Om PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/overview)
- [StackOverflow: PowerShell](https://stackoverflow.com/questions/tagged/powershell)
