---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:56.801945-07:00
description: "JSON eli JavaScript Object Notation on kevyt tiedonvaihtoformaatti,\
  \ joka on ihmisten luettavissa ja kirjoitettavissa helposti, sek\xE4 koneiden j\xE4\
  sent\xE4m\xE4 ja\u2026"
lastmod: '2024-03-13T22:44:56.677154-06:00'
model: gpt-4-0125-preview
summary: "JSON eli JavaScript Object Notation on kevyt tiedonvaihtoformaatti, joka\
  \ on ihmisten luettavissa ja kirjoitettavissa helposti, sek\xE4 koneiden j\xE4sent\xE4\
  m\xE4 ja tuottama vaivattomasti."
title: "Ty\xF6skentely JSON:n kanssa"
weight: 38
---

## Kuinka:
Työskentely JSONin kanssa PHP:ssä on suoraviivaista kiitos sisäänrakennettujen funktioiden `json_encode()` ja `json_decode()`. Alla on esimerkkejä, jotka näyttävät, kuinka PHP-taulukko muunnetaan JSON-merkkijonoksi ja päinvastoin:

### PHP-taulukon koodaaminen JSON-merkkijonoksi
```php
// Määritelty assosiatiivinen taulukko
$data = [
    "name" => "John Doe",
    "age" => 30,
    "email" => "john.doe@example.com"
];

// Muunna PHP-taulukko JSON-merkkijonoksi
$jsonString = json_encode($data);

// Tulosta JSON-merkkijono
echo $jsonString;
```
**Esimerkkituloste:**
```json
{"name":"John Doe","age":30,"email":"john.doe@example.com"}
```

### JSON-merkkijonon purkaminen PHP-taulukoksi
```php
// JSON-merkkijono
$jsonString = '{"name":"John Doe","age":30,"email":"john.doe@example.com"}';

// Muunna JSON-merkkijono PHP-taulukoksi
$data = json_decode($jsonString, true);

// Tulosta PHP-taulukko
print_r($data);
```
**Esimerkkituloste:**
```
Array
(
    [name] => John Doe
    [age] => 30
    [email] => john.doe@example.com
)
```

### Työskentely kolmannen osapuolen kirjaston kanssa: GuzzleHttp
Monimutkaisen JSON- ja web-pyyntöjen käsittelyyn yksi suosittu PHP-kirjasto on GuzzleHttp. Se yksinkertaistaa HTTP-pyyntöjä ja toimii helposti JSON-tietojen kanssa.

**Asennus Composerin kautta:**
```
composer require guzzlehttp/guzzle
```

**Esimerkkipyyntö:**
```php
require 'vendor/autoload.php';

use GuzzleHttp\Client;

$client = new Client();

// Lähetä pyyntö API:lle, joka palauttaa JSONia
$response = $client->request('GET', 'https://api.example.com/data', [
    'headers' => [
        'Accept' => 'application/json',
    ],
]);

// Pure JSON-vaste PHP-taulukoksi
$data = json_decode($response->getBody(), true);

// Tulosta data
print_r($data);
```

**Olettaen, että API palauttaa samankaltaisia JSON-tietoja:**
```
Array
(
    [name] => John Doe
    [age] => 30
    [email] => john.doe@example.com
)
```
Tämä esittelee PHP:n helppokäyttöisyyden JSONin käsittelyssä, sekä natiivien funktioiden että monimutkaisempiin tehtäviin tarkoitettujen, kuten GuzzleHttp-kirjaston avulla.
