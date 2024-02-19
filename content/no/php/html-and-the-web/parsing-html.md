---
aliases:
- /no/php/parsing-html/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:46.454658-07:00
description: "Parsing av HTML i PHP involverer \xE5 trekke ut spesifikk informasjon\
  \ fra HTML-dokumenter. Utviklere utf\xF8rer denne oppgaven for \xE5 automatisere\
  \ datautvinning,\u2026"
lastmod: 2024-02-18 23:08:53.973212
model: gpt-4-0125-preview
summary: "Parsing av HTML i PHP involverer \xE5 trekke ut spesifikk informasjon fra\
  \ HTML-dokumenter. Utviklere utf\xF8rer denne oppgaven for \xE5 automatisere datautvinning,\u2026"
title: Analysering av HTML
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Parsing av HTML i PHP involverer å trekke ut spesifikk informasjon fra HTML-dokumenter. Utviklere utfører denne oppgaven for å automatisere datautvinning, webskraping, eller for å integrere innhold fra ulike nettsider i sine applikasjoner, noe som forbedrer funksjonaliteten uten manuell inngripen.

## Hvordan:
For å parse HTML, kan PHP-utviklere utnytte innebygde funksjoner eller støtte seg på robuste biblioteker som Simple HTML DOM Parser. Her vil vi utforske eksempler ved å bruke både PHPs `DOMDocument` og Simple HTML DOM Parser.

### Bruke `DOMDocument`:
PHPs `DOMDocument`-klasse er en del av dens DOM-utvidelse, som tillater parsing og manipulering av HTML- og XML-dokumenter. Her er et raskt eksempel på hvordan du bruker `DOMDocument` for å finne alle bildene i et HTML-dokument:

```php
$html = <<<HTML
<!DOCTYPE html>
<html>
<head>
    <title>Eksempelside</title>
</head>
<body>
    <img src="bilde1.jpg" alt="Bilde 1">
    <img src="bilde2.jpg" alt="Bilde 2">
</body>
</html>
HTML;

$doc = new DOMDocument();
@$doc->loadHTML($html);
$images = $doc->getElementsByTagName('img');

foreach ($images as $img) {
    echo $img->getAttribute('src') . "\n";
}
```

Eksempel på utdata:
```
bilde1.jpg
bilde2.jpg
```

### Bruke Simple HTML DOM Parser:
For mer komplekse oppgaver eller enklere syntaks, kan du foretrekke å bruke et tredjepartsbibliotek. Simple HTML DOM Parser er et populært valg, som tilbyr et jQuery-lignende grensesnitt for navigering og manipulasjon av HTML-strukturer. Her er hvordan du bruker det:

Først, installer biblioteket ved hjelp av Composer:
```
composer require simple-html-dom/simple-html-dom
```

Deretter, manipuler HTML for å, for eksempel, finne alle lenker:

```php
require_once 'vendor/autoload.php';

use simplehtmldom\HtmlWeb;

$client = new HtmlWeb();
$html = $client->load('http://www.eksempel.com');

foreach($html->find('a') as $element) {
    echo $element->href . "\n";
}
```

Dette kodeutdraget vil hente HTML-innholdet fra 'http://www.eksempel.com', parse det, og skrive ut alle hyperlenkene. Husk å erstatte `'http://www.eksempel.com'` med den faktiske URL-en du ønsker å parse.

Ved å bruke disse metodene kan PHP-utviklere effektivt parse HTML-innhold, tilpasse datautvinning etter sine behov, eller sømløst integrere eksternt webinnhold i sine prosjekter.
