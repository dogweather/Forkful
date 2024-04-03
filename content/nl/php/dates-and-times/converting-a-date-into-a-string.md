---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:57:16.089729-07:00
description: "Het omzetten van een datum naar een tekenreeks betekent het veranderen\
  \ van een datumobject in een platte-tekstformaat. Programmeurs doen dit voor\u2026"
lastmod: '2024-03-13T22:44:50.907261-06:00'
model: gpt-4-0125-preview
summary: Het omzetten van een datum naar een tekenreeks betekent het veranderen van
  een datumobject in een platte-tekstformaat.
title: Een datum converteren naar een string
weight: 28
---

## Hoe te:
In PHP zet de `date()` functie een tijdstempel om in een beter leesbare tekenreeks. Het `DateTime` object dient een soortgelijk doel met zijn `format()` methode. Zo zien ze er in de praktijk uit:

```php
<?php
// Gebruikmakend van de date() functie
echo date('Y-m-d H:i:s') . "\n"; // uitvoer: 2023-04-03 14:30:00 (voorbeeld)

// Gebruikmakend van het DateTime object
$dateTime = new DateTime();
echo $dateTime->format('Y-m-d H:i:s') . "\n"; // uitvoer: identiek
?>
```
De voorbeelduitvoer weerspiegelt de datum en tijd waarop de code werd uitgevoerd.

## Diepgaand
Historisch gezien is PHP geëvolueerd in de behandeling van datum en tijd. Eerdere PHP-versies hadden minder kenmerken voor datummanipulatie. De `DateTime` klasse, geïntroduceerd in PHP 5.2.0, bood objectgeoriënteerde behandeling, ondersteuning voor tijdzones en meer veelzijdigheid.

Alternatieven voor `date()` en `DateTime` zijn onder andere:
- `strftime()` (locale-bewuste formattering)
- `DateTimeImmutable` (onveranderlijke versie van `DateTime`)
- Uitbreidingsklassen zoals `Carbon` voor complexere behoeften

Intern vertrouwen zowel `date()` als `DateTime` op de tijdzone-instellingen van de server, tenzij anders aangegeven. De `DateTimeZone` klasse kan tijdzones manipuleren.

## Zie Ook
- [PHP Handleiding: Datum- en Tijdfuncties](https://www.php.net/manual/en/book.datetime.php)
- [PHP op de Juiste Manier: Datums en Tijden](https://phptherightway.com/#date_and_time)
- [Carbon: Een simpele PHP API uitbreiding voor DateTime](https://carbon.nesbot.com/)
