---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:59:30.494620-07:00
description: "\xC5 lese kommandolinjeargumenter i Visual Basic for Applications (VBA)\
  \ inneb\xE6rer \xE5 f\xE5 tilgang til parametere som er sendt til programmet ditt\
  \ ved utf\xF8relse.\u2026"
lastmod: '2024-03-13T22:44:40.637825-06:00'
model: gpt-4-0125-preview
summary: "\xC5 lese kommandolinjeargumenter i Visual Basic for Applications (VBA)\
  \ inneb\xE6rer \xE5 f\xE5 tilgang til parametere som er sendt til programmet ditt\
  \ ved utf\xF8relse."
title: Lese kommandolinje-argumenter
weight: 23
---

## Hvordan:
I motsetning til mer rettframme programmeringsmiljøer, har ikke VBA en innebygd funksjon for å direkte lese kommandolinjeargumenter i tradisjonell forstand fordi det primært er designet for å bli integrert innen Microsoft Office-applikasjoner. Imidlertid, med litt kreativitet, kan vi bruke Windows Script Host (WSH) eller kalle eksterne APIer for å oppnå lignende funksjonalitet. Her er en praktisk omgåelse ved bruk av WSH:

1. **Lag et VBScript for å Sende Argumenter til VBA:**

   Først, skriv en VBScript-fil (*dittSkript.vbs*) som starter VBA-applikasjonen din (f.eks. en Excel-makro) og sender kommandolinjeargumentene:

```vb
Set objExcel = CreateObject("Excel.Application")
objExcel.Workbooks.Open "C:\YourMacroWorkbook.xlsm"
objExcel.Run "YourMacroName", WScript.Arguments.Item(0), WScript.Arguments.Item(1)
objExcel.Quit
```

2. **Få Tilgang til Argumentene i VBA:**

   I VBA-applikasjonen din (*DinMakroArbeidsbok.xlsm*), endre eller opprett makroen (*DinMakroNavn*) for å akseptere parametere:

```vb
Sub DinMakroNavn(arg1 As String, arg2 As String)
    MsgBox "Argument 1: " & arg1 & " Argument 2: " & arg2
End Sub
```

3. **Kjør Ditt Skript:**

   Utfør VBScriptet fra kommandolinjen, ved å sende argumenter som nødvendig:

```shell
cscript dittSkript.vbs "Hallo" "Verden"
```

   Dette bør resultere i at VBA-makroen din blir utført med argumentene "Hallo" og "Verden", som vises i en meldingsboks.

## Dypdykk:
I en historisk kontekst ble VBA utviklet for å utvide funksjonaliteten til Microsoft Office-applikasjoner, ikke som et selvstendig programmeringsmiljø. Som sådan, er direkte interaksjon med kommandolinjen utenfor dets primære omfang, noe som forklarer mangelen på innebygd støtte for å lese kommandolinjeargumenter.

Metoden som er skissert ovenfor, selv om den er effektiv, er mer en omvei enn en naturlig løsning, og tar i bruk eksternt skripting for å tette gapet. Denne tilnærmingen kan introdusere kompleksitet og potensielle sikkerhetsproblemer, da det krever at makroer aktiveres og potensielt redusere sikkerhetsinnstillinger for å utføre.

For oppgaver som er sterkt avhengige av kommandolinjeargumenter, eller som trenger en mer sømløs integrasjon med Windows-operativsystemet, kan andre programmeringsspråk som PowerShell eller Python tilby mer robuste og sikre løsninger. Disse alternativene gir direkte støtte for kommandolinjeargumenter og er bedre egnet for selvstendige applikasjoner eller skript som krever ekstern inndata for å dynamisk endre oppførselen.
