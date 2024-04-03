---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:46.598586-07:00
description: "Een tekstbestand lezen betekent het verkrijgen van de inhoud van een\
  \ bestand in je script. Programmeurs doen dit om met gegevens, configuratie te werken\u2026"
lastmod: '2024-03-13T22:44:51.001210-06:00'
model: gpt-4-0125-preview
summary: Een tekstbestand lezen betekent het verkrijgen van de inhoud van een bestand
  in je script.
title: Een tekstbestand lezen
weight: 22
---

## Hoe:
Hier is de eenvoudigste manier om een bestand regel-voor-regel te lezen:

```Bash
while IFS= read -r line; do
    echo "Tekst: $line"
done < "jouwbestand.txt"
```

Wil je het hele bestand in één keer? Probeer dit:

```Bash
file_content=$(<jouwbestand.txt)
echo "$file_content"
```

Of heb je een specifieke regel nodig, zeg regel 4?

```Bash
sed '4q;d' jouwbestand.txt
```

Voorbeelduitvoer voor het lezen van regel 4:

```
Dit is de inhoud van regel vier.
```

## Diepere Duik
Vroeger hadden we geen chique IDE's, we hadden terminals en eenvoudige teksteditors. UNIX-tools waren ontworpen met een filosofie van één ding goed doen. `cat`, `less`, `sed`, en `awk` zijn veteranen in het manipuleren van tekst.

Een bestand lezen in Bash maakt gebruik van deze tools, plus Bash's eigen redirects en lussen. Bijvoorbeeld, het gebruik van `while` met `read` is goed voor geheugenefficiëntie met grote bestanden. Je leest regel voor regel, niet alles in het geheugen dumpen.

`sed` is een stream editor. Een specifieke regel pakken met `sed '4q;d' jouwbestand.txt` vertelt `sed` om te stoppen na regel 4 (`4q`) en dan die regel te printen (`;d`).

Er bestaan alternatieven. `awk` is krachtig voor tekstverwerking. Perl en Python-scripts kunnen binnen Bash worden aangeroepen als tekstverwerking complex wordt. Elk van deze tools en talen heeft zijn eigen gebruiksscenario's en prestatieoverwegingen.

## Zie Ook
1. Bash Scripting Handleiding: https://www.gnu.org/software/bash/manual/
2. `sed` en `awk` 101 Hacks: https://www.thegeekstuff.com/2009/12/unix-sed-tutorial-6-examples-to-edit-file-in-place/
3. Linux Command Line Tekstverwerking met `grep`, `awk`, `sed`, `sort`, en vrienden: https://github.com/learnbyexample/Command-line-text-processing
