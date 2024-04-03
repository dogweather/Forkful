---
date: 2024-01-20 17:56:36.195217-07:00
description: "Kommandolinjeargumenter lar deg kj\xF8re PHP-skript med spesifikke parametere\
  \ for ulike oppgaver. \xC5 bruke disse er n\xF8dvendig for \xE5 lage fleksible skript\
  \ som\u2026"
lastmod: '2024-03-13T22:44:40.901812-06:00'
model: gpt-4-1106-preview
summary: "Kommandolinjeargumenter lar deg kj\xF8re PHP-skript med spesifikke parametere\
  \ for ulike oppgaver."
title: Lese kommandolinjeargumenter
weight: 23
---

## How to:
PHP skript mottar kommandolinjeargumenter i `$argv` array og `$argc` variable. Her er et enkelt eksempel:

```php
<?php
// Sjekker om det er nok argumenter
if ($argc < 2) {
    echo "Bruk: php script.php [navn]\n";
    exit;
}

// Skriver ut det første argumentet
echo "Hei, " . $argv[1] . "!\n";

// Kjør: php script.php Verden
// Output: Hei, Verden!
```

## Deep Dive
Kommandolinjeargumenter har blitt brukt siden tidlige databehandlingsdager og er vanlige i mange programmeringsspråk. I PHP er `$argv` en array som inneholder argumentene og `$argc` er et tall som representerer antall argumenter. Bruk av disse er direkte og ubyråkratisk.

Alternativer for mer komplekse behov inkluderer `getopt()` funksjonen for flagg og verdier, eller tredjeparts biblioteker som Symfony's Console komponent.

Kjernedetaljer:
- `$argv[0]` er skriptnavnet.
- Argumentene starter fra `$argv[1]`.
- `getopt()` kan hente spesifikke options og verdier.

## See Also
- [PHP.net $argv](https://www.php.net/manual/en/reserved.variables.argv.php)
- [PHP.net $argc](https://www.php.net/manual/en/reserved.variables.argc.php)
- [PHP.net getopt](https://www.php.net/manual/en/function.getopt.php)
- [Symfony Console Component](https://symfony.com/doc/current/components/console.html)
