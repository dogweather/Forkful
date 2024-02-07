---
title:                "Analisi di una data da una stringa"
date:                  2024-02-03T19:14:59.590839-07:00
model:                 gpt-4-0125-preview
simple_title:         "Analisi di una data da una stringa"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/php/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa & Perché?

L'analisi di una data da una stringa in PHP implica la conversione di testo che rappresenta una data e/o un orario in un oggetto PHP `DateTime` o in altri formati di data/ora. Questo è fondamentale per scopi di validazione, manipolazione, memorizzazione e presentazione dei dati, specialmente quando si lavora con input dell'utente o dati da fonti esterne.

## Come fare:

La classe `DateTime` integrata in PHP offre un potente insieme di funzioni per l'analisi e la gestione delle date. Puoi creare un'istanza di `DateTime` da una stringa di data utilizzando il costruttore e poi formattarla come necessario. Ecco come:

```php
$dateString = "2023-04-25 15:30:00";
$dateObject = new DateTime($dateString);

echo $dateObject->format('Y-m-d H:i:s');
// Output: 2023-04-25 15:30:00
```

Per gestire stringhe che seguono formati non standard, puoi utilizzare il metodo `createFromFormat`, che ti consente di specificare l'esatto formato della data in input:

```php
$dateString = "25-04-2023 3:30 PM";
$dateObject = DateTime::createFromFormat('d-m-Y g:i A', $dateString);

echo $dateObject->format('Y-m-d H:i:s');
// Output: 2023-04-25 15:30:00
```

Per un'analisi più complessa che potrebbe non essere direttamente supportata da `DateTime`, PHP offre la funzione `strtotime`, che tenta di analizzare qualsiasi descrizione testuale inglese di data/ora in un timestamp Unix:

```php
$timestamp = strtotime("next Thursday");
echo date('Y-m-d', $timestamp);
// L'output varierà a seconda della data corrente, es. "2023-05-04"
```

**Uso di librerie di terze parti:**

Anche se le funzioni integrate di PHP coprono un'ampia gamma di casi d'uso, a volte potresti aver bisogno di capacità di analisi più sofisticate. La libreria Carbon, un'estensione della classe DateTime di PHP, fornisce un ricco insieme di funzionalità per la manipolazione di date/orari:

```php
require 'vendor/autoload.php';

use Carbon\Carbon;

$dateString = "Tomorrow";
$date = Carbon::parse($dateString);

echo $date->toDateTimeString();
// L'output varierà, es., "2023-04-26 00:00:00"
```

Il metodo `parse` di Carbon può gestire intelligentemente una moltitudine di formati di data e ora, rendendolo uno strumento inestimabile per applicazioni che richiedono una funzionalità di analisi della data flessibile.
