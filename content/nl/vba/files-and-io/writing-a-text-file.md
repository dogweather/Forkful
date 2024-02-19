---
aliases:
- /nl/vba/writing-a-text-file/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:08:19.376206-07:00
description: "Een tekstbestand schrijven in Visual Basic for Applications (VBA) houdt\
  \ in dat je tekstgegevens aanmaakt, wijzigt of toevoegt aan bestanden, een\u2026"
lastmod: 2024-02-18 23:09:01.686474
model: gpt-4-0125-preview
summary: "Een tekstbestand schrijven in Visual Basic for Applications (VBA) houdt\
  \ in dat je tekstgegevens aanmaakt, wijzigt of toevoegt aan bestanden, een\u2026"
title: Een tekstbestand schrijven
---

{{< edit_this_page >}}

## Wat & Waarom?

Een tekstbestand schrijven in Visual Basic for Applications (VBA) houdt in dat je tekstgegevens aanmaakt, wijzigt of toevoegt aan bestanden, een fundamentele taak voor het opslaan van uitvoer, loggen of interactie met andere applicaties. Programmeurs gebruiken deze functionaliteit om rapportage, data-export of generatie van configuratiebestanden binnen het Microsoft Office-ecosysteem te automatiseren.

## Hoe te:

VBA biedt verschillende methoden om naar een bestand te schrijven, maar een van de meest eenvoudige manieren is door gebruik te maken van het `FileSystemObject`. Hier is een stap-voor-stap handleiding om een eenvoudig tekstbestand te creëren en er data naar te schrijven:

1. **Verwijs naar Microsoft Scripting Runtime**: Zorg er eerst voor dat je VBA-editor toegang heeft tot het `FileSystemObject`. Ga naar Extra > Referenties in de VBA-editor en vink "Microsoft Scripting Runtime" aan.

2. **Maak een tekstbestand**: Het volgende VBA-codesnippet laat zien hoe je een tekstbestand creëert en er een regel tekst naar schrijft.

```vb
Sub WriteToFile()
    Dim fso As FileSystemObject
    Set fso = New FileSystemObject
    
    Dim textFile As Object
    ' CreateTextFile parameters: (Bestandsnaam, Overschrijven, Unicode)
    Set textFile = fso.CreateTextFile("C:\jouwPad\voorbeeld.txt", True, False)
    
    ' Schrijf een regel tekst
    textFile.WriteLine "Hallo, VBA!"
    
    ' Sluit het bestand
    textFile.Close
End Sub
```

Dit script creëert (of overschrijft indien al bestaand) een bestand met de naam `voorbeeld.txt` in de opgegeven directory en schrijft "Hallo, VBA!" erin voordat het bestand wordt gesloten om wijzigingen op te slaan.

3. **Voorbeelduitvoer**:

Na het uitvoeren van het bovenstaande VBA-script, vind je een bestand met de naam `voorbeeld.txt` met de volgende inhoud:

```
Hallo, VBA!
```

## Diepgaande duik:

Het `FileSystemObject` (FSO), onderdeel van de Microsoft Scripting Runtime-bibliotheek, biedt een rijke set aan eigenschappen en methoden voor bestandsbewerkingen, die verder reiken dan wat traditionele VBA-bestandsafhandeling biedt (bijv. `Open`, `Print` #, `Write` #). Naast het afhandelen van bestanden, kan FSO ook mappen en schijven manipuleren, waardoor het een krachtig instrument is voor bestandssysteembewerkingen binnen VBA.

Het is echter vermeldenswaardig dat hoewel FSO een modernere benadering van bestandsbewerkingen in VBA biedt, het mogelijk overhead introduceert voor eenvoudige taken in vergelijking met VBA's eigen bestandsafhandelingsinstructies. Bovendien, aangezien FSO deel uitmaakt van een externe bibliotheek, kunnen draagbaarheid en compatibiliteit met andere systemen (bijv. eerdere versies van Office, Mac Office) zorgen opleveren.

In contexten waar prestatie, compatibiliteit of minimale externe afhankelijkheden kritiek zijn, kunnen programmeurs overwegen om VBA’s ingebouwde bestandsbehandelingstechnieken te gebruiken. Echter, voor meer complexe operaties of wanneer men werkt in een omgeving waar deze zorgen worden verminderd (zoals in een gecontroleerde bedrijfssetting), wegen de voordelen van het FileSystemObject vaak op tegen de nadelen.
