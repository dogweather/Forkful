---
title:                "Arbeide med CSV"
aliases:
- no/php/working-with-csv.md
date:                  2024-02-03T19:20:58.195730-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeide med CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/php/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva og hvorfor?

Å jobbe med CSV (Comma-Separated Values), eller kommaseparerte verdier på norsk, innebærer å lese fra og skrive data til CSV-filer, et populært format for å representere tabulære data i ren tekst. Programmerere gjør dette for å enkelt utveksle data mellom ulike programmer, systemer eller databaser, takket være dets enkelhet og bred støtte på tvers av plattformer og programmeringsspråk.

## Hvordan:

PHP tilbyr innebygde funksjoner for håndtering av CSV-filer, noe som gjør det enkelt å lese fra og skrive til disse filene uten å måtte bruke tredjepartsbiblioteker. Her er eksempler for å komme i gang:

### Lese en CSV-fil

Du kan åpne en CSV-fil og lese innholdet ved hjelp av `fopen()` i kombinasjon med `fgetcsv()`:

```php
<?php
$filename = 'data.csv';
$handle = fopen($filename, "r");
if ($handle !== FALSE) {
    while (($data = fgetcsv($handle, 1000, ",")) !== FALSE) {
        $num = count($data);
        echo "Antall felt i linjen: $num\n";
        for ($c = 0; $c < $num; $c++) {
            echo $data[$c] . "\n";
        }
    }
    fclose($handle);
}
?>
```

Dette skriptet skriver ut antall felt i hver linje etterfulgt av innholdet i hvert felt.

### Skrive til en CSV-fil

For å skrive til en CSV-fil, bruk `fopen()` i skrivemodus (`w`) og `fputcsv()`:

```php
<?php
$liste = [
    ['ID', 'Navn', 'E-post'],
    [1, 'John Doe', 'john@example.com'],
    [2, 'Jane Doe', 'jane@example.com']
];

$handle = fopen('users.csv', 'w');

foreach ($liste as $rad) {
    fputcsv($handle, $rad);
}

fclose($handle);
?>
```

Dette skriptet oppretter en fil med navnet `users.csv` og skriver overskriften og to rader med data til den.

### Bruke et bibliotek: League\Csv

For mer avansert håndtering av CSV, tilbyr biblioteket `League\Csv` et robust sett med funksjoner. Etter å ha installert det via Composer (`composer require league/csv`), kan du bruke det for å lese og skrive CSV-data mer fleksibelt.

#### Lese med League\Csv

```php
<?php
require 'vendor/autoload.php';

use League\Csv\Reader;

$csv = Reader::createFromPath('data.csv', 'r');
$csv->setHeaderOffset(0); // Sett hvis du vil bruke den første raden som overskrift

$resultater = $csv->getRecords();
foreach ($resultater as $rad) {
    print_r($rad);
}
?>
```

Dette skriptet leser `data.csv`, behandler den første raden som kolonneoverskrifter, og skriver ut hver rad som et assosiativt array.

#### Skrive med League\Csv

```php
<?php
require 'vendor/autoload.php';

use League\Csv\Writer;

$csv = Writer::createFromPath('users_new.csv', 'w+');

$csv->insertOne(['ID', 'Navn', 'E-post']);
$csv->insertAll([
    [3, 'Alex Doe', 'alex@example.com'],
    [4, 'Anna Smith', 'anna@example.com']
]);

echo "Skrevet til users_new.csv med suksess.";
?>
```

Dette oppretter `users_new.csv` og skriver en overskriftsrad etterfulgt av to datarader.
