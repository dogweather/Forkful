---
title:                "Använda associativa arrayer"
date:                  2024-02-01T22:04:38.218821-07:00
model:                 gpt-4-0125-preview
simple_title:         "Använda associativa arrayer"
tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/vba/using-associative-arrays.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

Associativa arrayer, ofta kända som ordböcker i Visual Basic for Applications (VBA), gör det möjligt för programmerare att skapa samlingar av nyckel-värde-par. Denna funktion är avgörande för effektiv datalagring och hämtning, vilket erbjuder ett mer flexibelt och intuitivt sätt att hantera data än traditionella arrayindex.

## Hur man gör:

I VBA tillhandahåller `Dictionary`-objektet en funktionalitet som liknar associativa arrayer. Du måste först lägga till en referens till Microsoft Scripting Runtime för att använda den:

1. Gå i VBA-editorn till Verktyg > Referenser...
2. Markera "Microsoft Scripting Runtime" och klicka OK.

Så här deklarerar, fyller du på och åtkommer poster i en `Dictionary`:

```vb
Dim sampleDictionary As Dictionary
Set sampleDictionary = New Dictionary

' Lägger till poster
sampleDictionary.Add Key:="Name", Item:="John Doe"
sampleDictionary.Add Key:="Age", Item:=29
sampleDictionary.Add Key:="Occupation", Item:="Ingenjör"

' Åtkommer poster
Debug.Print sampleDictionary.Item("Name")  ' Utdata: John Doe
Debug.Print sampleDictionary.Item("Age")   ' Utdata: 29

' Kontrollerar om en nyckel finns
If sampleDictionary.Exists("Occupation") Then
    Debug.Print "Occupation Key Exists"
End If

' Tar bort poster
sampleDictionary.Remove("Occupation")

' Loopar genom dictionarien
For Each Key In sampleDictionary.Keys
    Debug.Print Key & ": " & sampleDictionary.Item(Key)
Next Key
```

## Fördjupning

`Dictionary`-objektet kopplar i bakgrunden till komponenter av Windows Scripting Host. Som sådant är det ett late-bound COM-objekt, vilket var ett vanligt sätt att utöka VBA:s funktionalitet tidigare. Dess användning i VBA kan avsevärt förbättra språkets förmåga att manipulera komplexa datamängder utan att påtvinga en stel struktur, som setts i traditionella arrayer eller Excel-intervaller.

En begränsning att ha i åtanke är att åtkomst till `Dictionary` kräver att man ställer in en referens till Microsoft Scripting Runtime, vilket kan komplicera distributionen av dina VBA-projekt. Alternativ som samlingar existerar inom VBA men saknar några nyckelfunktioner i `Dictionary`, såsom möjligheten att enkelt kontrollera existensen av en nyckel utan att utlösa ett fel.

I mer samtida programmeringssammanhang erbjuder språk som Python inbyggt stöd för associativa arrayer (även kända som ordböcker i Python) utan behov av att lägga till externa referenser. Detta inbyggda stöd förenklar processen och erbjuder mer avancerade funktioner direkt ur lådan. Dock, inom ramarna för VBA och för specifika applikationer inriktade på att automatisera uppgifter i Microsoft Office-sviten, förblir användningen av `Dictionary`-objektet en kraftfull och relevant metod för datastrukturer liknande associativa arrayer.
