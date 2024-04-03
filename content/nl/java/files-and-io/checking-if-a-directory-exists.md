---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:55:55.034884-07:00
description: "Controleren of een directory bestaat betekent verifi\xEBren dat deze\
  \ er is voordat je probeert bestanden erin te lezen of te schrijven. Programmeurs\
  \ doen dit\u2026"
lastmod: '2024-03-13T22:44:50.697020-06:00'
model: gpt-4-0125-preview
summary: "Controleren of een directory bestaat betekent verifi\xEBren dat deze er\
  \ is voordat je probeert bestanden erin te lezen of te schrijven."
title: Controleren of een directory bestaat
weight: 20
---

## Hoe te:
Hier is hoe je controleert of een directory bestaat met `java.nio.file`:

```java
import java.nio.file.Files;
import java.nio.file.Path;

public class DirectoryCheck {

    public static void main(String[] args) {
        Path directoryPath = Path.of("/pad/naar/directory");

        // Controleer of de directory bestaat
        boolean directoryExists = Files.exists(directoryPath);

        // Print het resultaat
        System.out.println("Bestaat de directory? " + directoryExists);
    }
}
```

Als je dit uitvoert, zal je console eenvoudigweg tonen:

```
Bestaat de directory? true // of false
```

Veel plezier ermee.

## Diepere Duik
Vroeger gebruikten mensen de `java.io.File.exists()` methode. Maar `java.nio.file.Files.exists(Path)` is nu de topper omdat het veelzijdiger is. Je kunt ook bestandsattributen met dezelfde API controleren.

Maar wacht, er is meer. De `Files.exists` methode is niet kogelvrij—er is een raceconditie. Wat als er iets met de directory gebeurt direct nadat je controleert? Bam, je operatie faalt. Om dit te vermijden, gebruik `Files.exists` spaarzaam en behandel uitzonderingen correct bij daadwerkelijke bestandsoperaties.

Als alternatief kun je simpelweg de bestandsoperatie proberen en de mogelijke `NoSuchFileException` opvangen. Dit staat bekend als "makkelijker om vergiffenis te vragen dan toestemming" (EAFP) versus "kijk voordat je springt" (LBYL), wat is wat `Files.exists()` doet.

## Zie Ook
- [Files.exists()](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Files.html#exists(java.nio.file.Path,java.nio.file.LinkOption...))
- [Bestand I/O in Java](https://docs.oracle.com/javase/tutorial/essential/io/)
- Een cool artikel over EAFP vs LBYL: [Het EAFP Principe](https://devblogs.microsoft.com/python/idiomatic-python-eafp-versus-lbyl/)
