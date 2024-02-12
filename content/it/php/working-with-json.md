---
title:                "Lavorare con JSON"
aliases:
- it/php/working-with-json.md
date:                  2024-02-03T19:23:36.914908-07:00
model:                 gpt-4-0125-preview
simple_title:         "Lavorare con JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/php/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa & Perché?
JSON, acronimo di JavaScript Object Notation, è un formato di scambio dati leggero facile da leggere e scrivere per gli esseri umani e da analizzare e generare per le macchine. I programmatori lavorano spesso con JSON per lo scambio di dati tra server e applicazioni web grazie alla sua semplicità e indipendenza dalla lingua, rendendolo un pilastro nello sviluppo web moderno e nelle API.

## Come fare:
Lavorare con JSON in PHP è semplice grazie alle funzioni incorporate `json_encode()` e `json_decode()`. Di seguito sono riportati esempi che mostrano come convertire un array PHP in una stringa JSON, e viceversa:

### Codificare un Array PHP in una Stringa JSON
```php
// Definisci un array associativo
$data = [
    "name" => "John Doe",
    "age" => 30,
    "email" => "john.doe@example.com"
];

// Converti l'array PHP in una stringa JSON
$jsonString = json_encode($data);

// Stampa la stringa JSON
echo $jsonString;
```
**Esempio di output:**
```json
{"name":"John Doe","age":30,"email":"john.doe@example.com"}
```

### Decodificare una Stringa JSON in un Array PHP
```php
// Stringa JSON
$jsonString = '{"name":"John Doe","age":30,"email":"john.doe@example.com"}';

// Converti la stringa JSON in un array PHP
$data = json_decode($jsonString, true);

// Stampa l'array PHP
print_r($data);
```
**Esempio di output:**
```
Array
(
    [name] => John Doe
    [age] => 30
    [email] => john.doe@example.com
)
```

### Lavorare con una Libreria di Terze Parti: GuzzleHttp
Per la gestione complessa di JSON e richieste web, una popolare libreria PHP è GuzzleHttp. Semplifica le richieste HTTP e lavora facilmente con i dati JSON.

**Installazione tramite Composer:**
```
composer require guzzlehttp/guzzle
```

**Esempio di richiesta:**
```php
require 'vendor/autoload.php';

use GuzzleHttp\Client;

$client = new Client();

// Invia una richiesta ad un'API che restituisce JSON
$response = $client->request('GET', 'https://api.example.com/data', [
    'headers' => [
        'Accept' => 'application/json',
    ],
]);

// Decodifica la risposta JSON in un array PHP
$data = json_decode($response->getBody(), true);

// Stampa i dati
print_r($data);
```

**Assumendo che l'API restituisca dati JSON simili:**
```
Array
(
    [name] => John Doe
    [age] => 30
    [email] => john.doe@example.com
)
```
Questo mostra la facilità di utilizzo di PHP per la manipolazione di JSON, sia con funzioni native sia con robuste librerie come GuzzleHttp per compiti più complessi.
