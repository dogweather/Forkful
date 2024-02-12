---
title:                "Werken met TOML"
aliases:
- /nl/php/working-with-toml/
date:                  2024-01-28T22:11:53.327687-07:00
model:                 gpt-4-0125-preview
simple_title:         "Werken met TOML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/php/working-with-toml.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
TOML, een afkorting voor Tom's Obvious, Minimal Language, is een gegevensformaat vergelijkbaar met JSON of YAML, maar makkelijker leesbaar voor mensen. Programmeurs gebruiken het voor configuratiebestanden omdat het eenvoudig is en goed vertaalt naar datastructuren.

## Hoe te:
Zorg eerst dat je een TOML-parserbibliotheek hebt geïnstalleerd, zoals `yosymfony/toml`. Laten we een TOML-bestand parsen:

```php
composer require yosymfony/toml

<?php
require 'vendor/autoload.php';

use Yosymfony\Toml\Toml;

$tomlString = <<<TOML
[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
connection_max = 5000
enabled = true
TOML;

$array = Toml::Parse($tomlString);

print_r($array);
```

Voorbeelduitvoer:

```
Array
(
    [database] => Array
        (
            [server] => 192.168.1.1
            [ports] => Array
                (
                    [0] => 8001
                    [1] => 8001
                    [2] => 8002
                )

            [connection_max] => 5000
            [enabled] => 1
        )

)
```
## Diepgaande Duik
TOML is in 2013 tot stand gekomen, ontworpen door GitHub mede-oprichter Tom Preston-Werner als een gebruiksvriendelijker alternatief voor XML en JSON voor configuratiebestanden. Terwijl JSON eenvoudig is voor machines, maakt de structuur van TOML het makkelijk op menselijke ogen, zonder de complexiteit van YAML.

Alternatieven voor TOML zijn JSON, YAML en XML. Elk heeft zijn sterke punten en toepassingsscenario’s. JSON is alomtegenwoordig en taalonafhankelijk; YAML is leesbaarder en ondersteunt commentaren, terwijl XML uitgebreid en breed ondersteund is.

Bij het implementeren van TOML in PHP, kijk je naar bibliotheken die de inhoud ervan naar PHP-arrays of -objecten parsen. `yosymfony/toml` is een PHP-parser die voldoet aan versie 0.4.0 van de TOML-specificatie. Om bij te blijven met de nieuwste updates, controleer altijd op nieuwere parsers of updates die de meest actuele TOML-versie ondersteunen (v1.0.0 op het moment van mijn laatste update).

## Zie Ook
- TOML-specificatie: <https://toml.io/>
- TOML-parser voor PHP (`yosymfony/toml`): <https://github.com/yosymfony/toml>
- Dataformaten vergelijken (XML, JSON, YAML, TOML): <https://www.loginradius.com/blog/engineering/comparing-data-interchange-formats/>
- PHP-pakketbeheerder (Composer): <https://getcomposer.org/>
