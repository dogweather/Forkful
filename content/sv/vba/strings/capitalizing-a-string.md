---
aliases:
- /sv/vba/capitalizing-a-string/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:49:29.826256-07:00
description: "Att skriva om en str\xE4ng med stora bokst\xE4ver i Visual Basic for\
  \ Applications (VBA) inneb\xE4r att konvertera det f\xF6rsta tecknet i varje ord\
  \ i en str\xE4ng till\u2026"
lastmod: 2024-02-18 23:08:51.608483
model: gpt-4-0125-preview
summary: "Att skriva om en str\xE4ng med stora bokst\xE4ver i Visual Basic for Applications\
  \ (VBA) inneb\xE4r att konvertera det f\xF6rsta tecknet i varje ord i en str\xE4\
  ng till\u2026"
title: "G\xF6r om en str\xE4ng till versaler"
---

{{< edit_this_page >}}

## Vad & Varför?

Att skriva om en sträng med stora bokstäver i Visual Basic for Applications (VBA) innebär att konvertera det första tecknet i varje ord i en sträng till versal, samtidigt som man ser till att resten är i gemen. Programmerare gör detta för datanormalisering, för att förbättra läsbarheten och för att säkerställa konsekvens över textuella datainmatningar eller visningar.

## Hur man gör:

VBA har inte en inbyggd funktion specifikt för att skriva om varje ord i en sträng med stora bokstäver, som vissa andra programmeringsspråk gör. Du kan dock uppnå detta genom att kombinera några metoder och funktioner som `UCase`, `LCase`, och `Mid`.

Här är ett enkelt exempel på hur man skriver om en sträng:

```vb
Function CapitalizeString(inputString As String) As String
    Dim words As Variant
    words = Split(inputString, " ")
    For i = LBound(words) To UBound(words)
        If Len(words(i)) > 0 Then
            words(i) = UCase(Left(words(i), 1)) & LCase(Mid(words(i), 2))
        End If
    Next i
    CapitalizeString = Join(words, " ")
End Function

Sub ExampleUsage()
    Dim exampleString As String
    exampleString = "hello world from VBA!"
    MsgBox CapitalizeString(exampleString) 'Output: "Hello World From Vba!"
End Sub
```

Funktionen `CapitalizeString` delar upp inmatningssträngen i ord, storstavar den första bokstaven i varje ord, och fogar sedan samman dem igen för att bilda en korrekt skriven sträng.

## Fördjupning

Visual Basic for Applications, som introducerades i början av 90-talet som ett makrospråk för Microsoft Office-applikationer, var utformad för att erbjuda en tillgänglig programmeringsmodell. Dess förmåga att manipulera strängar, även om omfattande, saknar vissa högre abstraktioner som finns i nyare språk. Många moderna programmeringsmiljöer tillhandahåller en dedikerad metod för att storstava strängar, ofta kallad titelhöjning eller liknande. Python inkluderar till exempel metoden `.title()` för strängar.

När man jämför kan avsaknaden av en enskild, inbyggd funktion i VBA för att storstava ord i strängar förefalla som en brist. Detta erbjuder dock programmerare en djupare förståelse och kontroll över hur de manipulerar text och hanterar nyanser som inte strikt följs av en generisk metod. Till exempel kan hanteringen av akronymer eller särskilda fall där vissa mindre ord i titlar inte bör storstavas anpassas bättre i VBA genom uttryckliga funktioner.

Vidare, även om direkta metoder finns i VBA för att ändra teckenstorlek på en sträng (`LCase` och `UCase`), betonar den manuella rutten för att storstava enskilda ord inom en sträng den nyanserade kontroll som VBA ger till utvecklare. Detta är särskilt viktigt i applikationer som databashantering, formulärinmatningar och redigering av dokument där textmanipulering är frekvent men varierad i krav.

Ändå, för applikationer där textbearbetningsbehoven är höga och mångsidiga, kan språk med inbyggda strängmanipuleringsbibliotek erbjuda en mer effektiv väg. Det är i dessa scenarier som integrering eller komplettering av VBA med andra programmeringsresurser, eller att välja ett annat språk helt och hållet, kan visa sig vara fördelaktigt.
