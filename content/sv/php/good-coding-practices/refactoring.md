---
date: 2024-01-26 01:55:11.952605-07:00
description: "Refaktorisering \xE4r processen att omstrukturera befintlig datorprogramkod\
  \ utan att \xE4ndra dess externa beteende. Programmerare refaktoriserar f\xF6r att\u2026"
lastmod: '2024-03-13T22:44:38.004598-06:00'
model: gpt-4-0125-preview
summary: "Refaktorisering \xE4r processen att omstrukturera befintlig datorprogramkod\
  \ utan att \xE4ndra dess externa beteende."
title: Refaktorisering
weight: 19
---

## Hur:
Låt oss ta en klassisk PHP-snutt och tillämpa lite refaktoriseringsmagi på den.

Innan refaktorisering kan vår kod se ut så här:

```php
function printOrderDetails($order) {
    foreach ($order as $item) {
        echo "Artikel: " . $item['name'];
        echo " - Pris: " . $item['price'];
        echo "<br>";
    }
    
    if (!empty($order)) {
        echo "Totalt: " . array_sum(array_column($order, 'price'));
    }
}
```

Men vi kan refaktorisera denna kod för att förbättra dess tydlighet och modularitet:

```php
function printItem($item) {
    echo "Artikel: {$item['name']} - Pris: {$item['price']}<br>";
}

function calculateTotal($order) {
    return array_sum(array_column($order, 'price'));
}

function printOrderDetails(array $order) {
    array_walk($order, 'printItem');

    if (!empty($order)) {
        echo "Totalt: " . calculateTotal($order);
    }
}
```
Genom att bryta ner funktionen `printOrderDetails` i mindre funktioner, blir vår kod mer läsbar och lättare att felsöka.

## Djupdykning
Refaktorisering har sina rötter i programmeringsgemenskapen för smalltalk i början av 1990-talet och populariserades ytterligare genom Martin Fowlers banbrytande bok "Refaktorisering: Att förbättra designen av befintlig kod" (1999). Även om refaktorisering kan tillämpas på vilket programmeringsspråk som helst, erbjuder PHP:s dynamiska natur vissa unika utmaningar och möjligheter.

Alternativ till refaktorisering kan inkludera att skriva om kod från grunden, vilket ofta är riskfyllt och mer tidskrävande. I PHP-ekosystemet kan verktyg som PHPStan och Rector automatiskt identifiera och utföra vissa refaktoriseringsoperationer respektive. När det gäller implementering är det viktigt att hålla refaktoriseringar små och testa omfattande med enhetstester för att säkerställa lyckad refaktorisering utan att introducera buggar.

## Se även
- Martin Fowlers bok om Refaktorisering: https://martinfowler.com/books/refactoring.html
- PHPStan, ett verktyg för statisk analys av PHP: https://phpstan.org/
- Rector, ett verktyg för automatisk refaktorisering av PHP-kod: https://getrector.org/
- PHP-enhetstestning med PHPUnit: https://phpunit.de/
