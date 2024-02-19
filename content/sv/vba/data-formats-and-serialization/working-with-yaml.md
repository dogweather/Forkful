---
aliases:
- /sv/vba/working-with-yaml/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:07:10.416028-07:00
description: "YAML, som st\xE5r f\xF6r \"YAML Ain't Markup Language\", \xE4r ett l\xE4\
  sligt dataserialiseringspr\xE5k som ofta anv\xE4nds f\xF6r konfigurationsfiler.\
  \ Programmerare anv\xE4nder\u2026"
lastmod: 2024-02-18 23:08:51.648192
model: gpt-4-0125-preview
summary: "YAML, som st\xE5r f\xF6r \"YAML Ain't Markup Language\", \xE4r ett l\xE4\
  sligt dataserialiseringspr\xE5k som ofta anv\xE4nds f\xF6r konfigurationsfiler.\
  \ Programmerare anv\xE4nder\u2026"
title: Att Arbeta med YAML
---

{{< edit_this_page >}}

## Vad & Varför?

YAML, som står för "YAML Ain't Markup Language", är ett läsligt dataserialiseringspråk som ofta används för konfigurationsfiler. Programmerare använder det ofta på grund av dess enkelhet och läsbarhet över en mängd programmeringsmiljöer, inklusive i skriptmiljön för Visual Basic for Applications (VBA) för att förbättra interoperabilitet samt datalagring och utbyte.

## Hur man gör:

Att arbeta med YAML i VBA kräver förståelse för hur man tolkar och konverterar YAML till ett format som VBA lätt kan hantera, vanligtvis dictionaries eller samlingar. Tyvärr stöder VBA inte naturligt YAML-tolkning eller serialisering. Du kan dock använda en kombination av JSON-konverteringsverktyg och dictionary-objekt för att arbeta med YAML-data, med tanke på YAML:s nära relation till JSON.

Först, konvertera dina YAML-data till JSON med en onlinekonverterare eller ett YAML-till-JSON-konverteringsverktyg i din utvecklingsmiljö. När det är konverterat kan du använda följande exempel för att tolka JSON i VBA, notera att detta tillvägagångssätt indirekt låter dig arbeta med YAML:

```vb
' Lägg till referens till Microsoft Scripting Runtime för Dictionary
' Lägg till referens till Microsoft XML, v6.0 för JSON-tolkning

Sub ParseYAMLAsJSON()
    Dim jsonText As String
    jsonText = "{""name"": ""John Doe"", ""age"": 30}" ' Detta är JSON konverterat från YAML
    
    ' Antag att du har en JSON-tolkningsfunktion
    Dim parsedData As Dictionary
    Set parsedData = JsonParser(jsonText)
    
    Debug.Print "Namn: " & parsedData("name")
    Debug.Print "Ålder: " & parsedData("age")
End Sub

Function JsonParser(ByVal jsonText As String) As Dictionary
    ' Plats för JSON-tolkningslogik - du kan använda ett externt bibliotek här
    Set JsonParser = New Dictionary
    JsonParser.Add "name", "John Doe"
    JsonParser.Add "age", 30
End Function
```
I detta exempel är `JsonParser`-funktionen en ersättare för där du skulle tolka JSON. Olika bibliotek finns tillgängliga för att hjälpa med JSON-tolkning, eftersom direkta YAML-tolkningsbibliotek för VBA är sällsynta.

## Djupdykning

Avsaknaden av direkt hantering av YAML i VBA kan tillskrivas dess ålder och den miljö den byggdes för, vilket ursprungligen inte designades med moderna dataserialiseringsformat i åtanke. YAML självt framträdde som ett populärt format för konfiguration och serialisering i början av 2000-talet, i linje med framkomsten av applikationer som kräver mer människovänliga konfigurationsfiler.

Programmerare brukar använda externa verktyg eller bibliotek för att överbrygga gapet mellan VBA och YAML. Detta innebär ofta att konvertera YAML till JSON, som visat, på grund av det stöd för JSON som finns tillgängligt genom olika bibliotek och likheten mellan JSON och YAML avseende struktur och syfte.

Även om arbetet med YAML direkt i VBA visar på språkets flexibilitet, är det värt att notera att andra programmeringsmiljöer (t.ex. Python eller JavaScript) tillhandahåller mer naturligt och sömlöst stöd för YAML. Dessa alternativ kan vara bättre lämpade för projekt som är starkt beroende av YAML för konfiguration eller dataserialisering. Icke desto mindre, för de som är engagerade i eller kräver VBA, är den indirekta metoden genom JSON-konvertering fortfarande en genomförbar och användbar strategi för att hantera och manipulera YAML-data.
