---
title:                "Arbeta med JSON"
aliases:
- sv/vba/working-with-json.md
date:                  2024-02-01T22:05:53.580669-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeta med JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/vba/working-with-json.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

JSON (JavaScript Object Notation) är ett lättviktigt datautbytesformat som är enkelt för människor att läsa och skriva, samt för maskiner att tolka och generera. Programmerare använder JSON för att överföra data mellan en server och en webbapplikation eller för att lagra information på ett strukturerat, åtkomligt sätt inom en mängd olika programmeringsmiljöer, inklusive Visual Basic for Applications (VBA).

## Hur man gör:

VBA stöder inte nativt tolkning eller generering av JSON, så vi kommer att använda ett skriptspråk som JScript (via ScriptControl-objektet) för att tolka JSON-strängar och bygga JSON-objekt. Så här kan du tolka en JSON-sträng i VBA:

```basic
Function ParseJSON(ByVal jsonString As String) As Object
    Dim scriptControl As Object
    Set scriptControl = CreateObject("MSScriptControl.ScriptControl")
    scriptControl.Language = "JScript"
    
    scriptControl.Eval "var obj = (" & jsonString & ")"
    Set ParseJSON = scriptControl.CodeObject.obj
End Function

Sub DemoParseJSON()
    Dim jsonString As String
    jsonString = "{""name"":""John"", ""age"":30, ""city"":""New York""}"
    
    Dim parsed As Object
    Set parsed = ParseJSON(jsonString)
    
    MsgBox "Namn: " & parsed.name & ", Ålder: " & parsed.age & ", Stad: " & parsed.city
End Sub
```

För att generera JSON kan du använda en liknande metod, där du bygger upp JSON-strängen genom sammanfogning:

```basic
Function GenerateJSON(name As String, age As Integer, city As String) As String
    GenerateJSON = "{""name"":""" & name & """, ""age"":" & age & ", ""city"":""" & city & """}"
End Function

Sub DemoGenerateJSON()
    Dim jsonString As String
    jsonString = GenerateJSON("Jane", 28, "Los Angeles")
    
    MsgBox jsonString
End Sub
```

## Fördjupning

De angivna metoderna använder sig av ScriptControl för att hantera JSON, vilket i huvudsak är att lägga ut arbetet på en JavaScript-motor. Detta är en kreativ lösning men inte nödvändigtvis det mest effektiva eller moderna sättet att arbeta med JSON i en VBA-kontext. I mer komplexa applikationer kan denna metod bli besvärlig och introducera prestandaproblem eller säkerhetsfrågor, eftersom ScriptControl körs i en miljö som har full åtkomst till värddatorn.

Andra programmeringsmiljöer, som Python eller JavaScript, erbjuder inbyggt stöd för JSON, vilket gör dem mer lämpliga för applikationer som kräver omfattande manipulering av JSON. Dessa språk tillhandahåller heltäckande bibliotek som underlättar inte bara tolkning och generering utan även frågeställningar och formatering av JSON-data.

Trots dessa begränsningar i VBA är förståelsen för hur man arbetar med JSON avgörande i en värld där webbaserat datautbyte och konfigurationsfiler huvudsakligen är formaterade i JSON. För VBA-programmerare öppnar mästerandet av dessa tekniker möjligheter att integrera med webb-API:er, tolka konfigurationsfiler eller till och med bygga enkla webbapplikationer. Men när projekt växer i komplexitet eller kräver hög prestanda kan utvecklare överväga att använda mer JSON-vänliga programmeringsmiljöer.
