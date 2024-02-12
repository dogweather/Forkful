---
title:                "Werken met YAML"
aliases:
- /nl/ruby/working-with-yaml/
date:                  2024-01-28T22:11:54.482620-07:00
model:                 gpt-4-0125-preview
simple_title:         "Werken met YAML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/ruby/working-with-yaml.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
YAML staat voor "YAML Ain't Markup Language." Het is een voor mensen leesbare gegevensserialisatieformaat. Programmeurs gebruiken het voor configuratiebestanden, gegevensuitwisseling tussen talen, en omdat het leesbaarder is dan JSON of XML voor complexe gegevensstructuren.

## Hoe te:

Om met YAML in Ruby te werken heb je de `yaml` bibliotheek nodig. Het maakt deel uit van de standaardbibliotheek van Ruby, dus je hoeft het alleen maar te vereisen:

```ruby
require 'yaml'
```

Om een Ruby hash naar een YAML-string te dumpen:

```ruby
require 'yaml'

my_hash = { name: 'Sam', occupation: 'Ontwikkelaar', hobbies: ['coderen', 'schaken'] }

yaml_string = my_hash.to_yaml
puts yaml_string
```

De uitvoer zal een YAML-geformatteerde string zijn:

```
---
:name: Sam
:occupation: Ontwikkelaar
:hobbies:
- coderen
- schaken
```

Om een YAML-string in Ruby te laden:

```ruby
require 'yaml'

yaml_string = "
name: Sam
occupation: Ontwikkelaar
hobbies:
  - coderen
  - schaken
"

ruby_hash = YAML.load(yaml_string)
puts ruby_hash
```

De uitvoer is een Ruby-hash:

```
{name: 'Sam', occupation: 'Ontwikkelaar', hobbies: ['coderen', 'schaken']}
```

## Diepteduik

YAML dook op in de vroege jaren 2000 als een mensvriendelijk alternatief voor XML voor configuratiebestanden en gegevensserialisatie. Het ontwerp maakt eenvoudige toewijzing naar inheemse gegevensstructuren mogelijk in veel talen, met implementaties in Python, Ruby, Java, PHP, en anderen.

Alternatieven voor YAML zijn JSON en TOML. JSON is gebruikelijker voor web-API’s vanwege de directe compatibiliteit met JavaScript. TOML streeft ernaar leesbaarder te zijn als een configuratiebestand en biedt een vergelijkbare functieset als YAML.

In Ruby wordt YAML geïmplementeerd door de Psych-bibliotheek, die sinds Ruby 1.9.3 de standaard YAML-parser is geweest. Psych werkt samen met libyaml, een C-bibliotheek voor YAML-parsing en -emitting.

## Zie Ook

- [De Officiële YAML-Website](https://yaml.org/)
- [Psych Bibliotheekdocumentatie](https://ruby-doc.org/stdlib-3.0.0/libdoc/psych/rdoc/Psych.html)
- [Ruby YAML Module Documentatie](https://ruby-doc.org/stdlib-2.5.1/libdoc/yaml/rdoc/YAML.html)
- [JSON (JavaScript Object Notation) Officiële Site](https://www.json.org/)
- [TOML (Tom's Obvious, Minimal Language) GitHub Repository](https://github.com/toml-lang/toml)
