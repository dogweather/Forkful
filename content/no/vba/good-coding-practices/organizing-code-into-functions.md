---
title:                "Organisering av kode i funksjoner"
aliases:
- no/vba/organizing-code-into-functions.md
date:                  2024-02-01T21:57:34.267441-07:00
model:                 gpt-4-0125-preview
simple_title:         "Organisering av kode i funksjoner"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/vba/organizing-code-into-functions.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Å organisere kode i funksjoner i Visual Basic for Applications (VBA) innebærer å bryte ned et program i mindre, håndterbare deler kjent som funksjoner. Programmerere gjør dette for å øke kodelesbarheten, gjenbruke kode effektivt, og forenkle feilsøking og vedlikeholdsprosesser.

## Hvordan:

I VBA defineres funksjoner ved å bruke `Function` og `End Function`-uttalelsene. Her er et enkelt eksempel på hvordan du oppretter en funksjon som beregner arealet av et rektangel:

```basic
Function CalculateArea(lengde As Double, bredde As Double) As Double
    CalculateArea = lengde * bredde
End Function
```

For å kalle på denne funksjonen i VBA-koden din og vise resultatet i en meldingsboks, ville du bruke:

```basic
Sub ShowArea()
    Dim areal As Double
    areal = CalculateArea(10, 5)
    MsgBox "Arealet er " & areal
End Sub
```

Når utført, viser denne koden en meldingsboks som sier: `Arealet er 50`.

### Overføre Variabler ByRef og ByVal

VBA lar deg overføre variabler til funksjoner enten ved referanse (`ByRef`) eller ved verdi (`ByVal`). Det første betyr at den originale variabelen kan modifiseres av funksjonen, mens det sistnevnte overfører en kopi, og beskytter den originale variabelen mot endringer.

```basic
Function ModifyValue(ByRef num As Integer)
    num = num + 5
End Function

Function PreserveValue(ByVal num As Integer) As Integer
    num = num + 5
    PreserveValue = num
End Function
```

## Dypdykk

VBA, som et hendelsesdrevet programmeringsspråk, legger betydelig vekt på funksjoner og subrutiner for å håndtere ulike oppgaver. I motsetning til mange moderne språk, har VBA en unik egenskap der `Function`-nøkkelordet ikke bare erklærer en blokk med gjenbrukbar kode, men også tillater en implisitt returverdi direkte tildelt til funksjonens navn.

Historisk sett har designet av VBA-funksjoner vært påvirket av tidligere programmeringsparadigmer der innkapsling og modularitet gradvis ble anerkjent for deres betydning i programvareutviklingen. Denne historiske bakgrunnen har ført til at VBA adopterte en noe konservativ, men funksjonell tilnærming til organisering av kode.

Selv om VBA er kraftig innenfor sine native omgivelser (f.eks., Microsoft Office-applikasjoner), er det viktig å merke seg at programmeringsverdenen har utviklet seg. Språk som Python tilbyr en mer grei syntaks og et veldig omfattende standardbibliotek, og gjør dem til et gunstig alternativ for ulike applikasjoner utenfor Office-suiten. Imidlertid, når man arbeider innenfor Microsoft Office-produkter, er integrerings- og automatiseringskapasitetene som VBA tilbyr uovertruffen.

Det er verdt å merke seg at til tross for sin alder, forblir samfunnet rundt VBA aktivt, og finner kontinuerlig innovative måter å utnytte dets funksjonalitet på. Men, ettersom programvareindustrien beveger seg mot mer moderne, allsidige og robuste språk, oppfordres programmerere kjent med VBA til å utforske disse alternativene for oppgaver som ikke er relatert til Office for å utvide verktøykassen for koding.
