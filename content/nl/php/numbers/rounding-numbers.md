---
title:                "Afronden van getallen"
aliases:
- /nl/php/rounding-numbers/
date:                  2024-01-28T22:06:54.251152-07:00
model:                 gpt-4-0125-preview
simple_title:         "Afronden van getallen"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/php/rounding-numbers.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Getallen afronden betekent het afhakken van decimale getallen tot een vastgelegde nauwkeurigheid, vaak tot hele getallen. Programmeurs ronden af om berekeningen te vereenvoudigen, prestaties te verbeteren of uitvoer gebruiksvriendelijker te maken.

## Hoe:
PHP biedt een paar manieren om getallen af te ronden: `round()`, `ceil()` en `floor()`. Hier is hoe ze werken:

```php
echo round(3.14159);   // Geeft 3 terug
echo round(3.14159, 2); // Geeft 3.14 terug

echo ceil(3.14159);    // Geeft 4 terug, rondt altijd omhoog

echo floor(3.14159);   // Geeft 3 terug, rondt altijd omlaag
```

## Diepere Duik
Het afronden van getallen is sinds de oudheid essentieel in wiskunde en berekening om om te gaan met onpraktische oneindige decimalen. In PHP kan `round()` een precisieparameter en modus nemen, die het gedrag beïnvloedt - `PHP_ROUND_HALF_UP`, `PHP_ROUND_HALF_DOWN`, enz., bepalen hoe het zal gedragen wanneer het een ".5" scenario tegenkomt. Nauwkeurigheid is essentieel in financiële toepassingen waar afronding wettelijk gereguleerd kan zijn, wat beïnvloedt hoe `round()` in de code wordt geïmplementeerd.

Alternatieven voor ingebouwde functies omvatten aangepaste afrondingsmethoden of BC Math-functies voor rekenkunde met willekeurige precisie, die nuttig zijn voor scenario's die meer controle vereisen of omgaan met zeer grote getallen waar de native nauwkeurigheid tekort kan schieten.

## Zie Ook
Verken meer in de PHP-handleiding:
- [PHP `round` functie](https://php.net/manual/en/function.round.php)
- [PHP `ceil` functie](https://php.net/manual/en/function.ceil.php)
- [PHP `floor` functie](https://php.net/manual/en/function.floor.php)
- [BC Math voor rekenkunde met willekeurige precisie](https://php.net/manual/en/book.bc.php)
