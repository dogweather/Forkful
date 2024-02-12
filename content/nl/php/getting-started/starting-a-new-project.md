---
title:                "Een nieuw project starten"
aliases:
- /nl/php/starting-a-new-project/
date:                  2024-01-28T22:08:20.695576-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een nieuw project starten"

tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/php/starting-a-new-project.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Een nieuw PHP-project starten betekent een basis opzetten om je webapp of script op te bouwen. We doen dit om fris te starten, onze ideeën in code te structureren, en nieuwe problemen op te lossen.

## Hoe te:
Begin je project door een structuur te kiezen. Composer is hier je vriend. Voer dit uit:

```bash
composer init
```

Maak vervolgens je `index.php`. Dat is je startpunt:

```php
<?php
// index.php
echo "Welkom bij mijn nieuwe PHP-project!";
```

Test het op je lokale server. Je zou moeten zien:

```
Welkom bij mijn nieuwe PHP-project!
```

## Diepere Duik
In het verleden begonnen PHP-projecten met eenvoudige scripts. Geen packagebeheer, geen frameworks, gewoon puur PHP-bestanden. Nu hebben we Composer, een tool om afhankelijkheden te beheren, klassen automatisch te laden en autolaadstandaarden zoals PSR-4 in te stellen. Het is standaardpraktijk voor moderne PHP-projecten.

Je zou ouderwets te werk kunnen gaan, geen Composer, geen autoladers. Maar waarom zou je het gemak en de breed geadopteerde standaarden negeren?

Gebruik frameworks zoals Laravel of Symfony voor complexe apps. Ze bieden structuur en tools, waardoor de ontwikkeling versnelt. Voor kleinere projecten kunnen micro-frameworks zoals Slim genoeg zijn.

Wat betreft de implementatie, overweeg omgevingsvariabelen voor configuratie, adopteer PSR-standaarden voor coderingsstijl en structuur, en sla een versiebeheersysteem zoals Git niet over.

## Zie Ook
- [Composer](https://getcomposer.org/)
- [PHP Op De Juiste Manier](https://phptherightway.com/)
- [PSR-standaarden](https://www.php-fig.org/psr/)
- [Laravel](https://laravel.com/)
- [Symfony](https://symfony.com/)
- [Slim Framework](http://www.slimframework.com/)
