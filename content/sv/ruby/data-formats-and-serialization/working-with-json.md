---
aliases:
- /sv/ruby/working-with-json/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:02.752073-07:00
description: "JSON (JavaScript Object Notation) \xE4r ett l\xE4ttviktigt datautbytesformat,\
  \ som \xE4r utbrett i webbapplikationer f\xF6r datav\xE4xling mellan klienter och\
  \ servrar.\u2026"
lastmod: 2024-02-18 23:08:52.315731
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) \xE4r ett l\xE4ttviktigt datautbytesformat,\
  \ som \xE4r utbrett i webbapplikationer f\xF6r datav\xE4xling mellan klienter och\
  \ servrar.\u2026"
title: Arbeta med JSON
---

{{< edit_this_page >}}

## Vad & Varför?

JSON (JavaScript Object Notation) är ett lättviktigt datautbytesformat, som är utbrett i webbapplikationer för dataväxling mellan klienter och servrar. Programmerare arbetar med JSON i Ruby för att tolka data som mottagits från externa källor eller för att formatera data för API-svar, och utnyttjar dess lättlästa struktur för enkel datamanipulation och lagring.

## Hur:

Ruby, med sitt standardbibliotek, erbjuder sömlösa sätt att tolka och generera JSON. Den primära modulen för dessa operationer är `json`, som enkelt kan integreras i vilken Ruby-applikation som helst.

### Tolka JSON:

För att konvertera en JSON-sträng till en Ruby-hash kan du använda metoden `JSON.parse`.

```ruby
require 'json'

json_strang = '{"name": "John Doe", "age": 30, "city": "New York"}'
ruby_hash = JSON.parse(json_strang)

puts ruby_hash
# Utdata: {"name"=>"John Doe", "age"=>30, "city"=>"New York"}
```

### Generera JSON:

Tvärtemot, för att omvandla en Ruby-hash till en JSON-sträng, använder du metoden `JSON.generate` eller metoden `to_json` som är tillgänglig på Ruby-objekt när `json`-biblioteket är inkluderat.

```ruby
require 'json'

ruby_hash = { name: "Jane Doe", age: 25, city: "Los Angeles" }
json_strang = ruby_hash.to_json

puts json_strang
# Utdata: {"name":"Jane Doe","age":25,"city":"Los Angeles"}
```

### Tredjepartsbibliotek:

Även om Rubys standardbibliotek täcker grundläggande hantering av JSON, förlitar sig många projekt på tredjepartsbibliotek för förbättrad funktionalitet och prestanda. Ett populärt val är `Oj` (Optimized JSON).

#### Tolka med Oj:

```ruby
require 'oj'

json_strang = '{"name": "Alex", "age": 40, "city": "Chicago"}'
ruby_hash = Oj.load(json_strang)

puts ruby_hash
# Utdata: {"name"=>"Alex", "age"=>40, "city"=>"Chicago"}
```

#### Generera med Oj:

Oj erbjuder också ett snabbt sätt att generera JSON från Ruby-objekt:

```ruby
require 'oj'

ruby_hash = { name: "Samantha", age: 35, city: "Miami" }
json_strang = Oj.dump(ruby_hash)

puts json_strang
# Utdata: {"name":"Samantha","age":35,"city":"Miami"}
```

Dessa exempel illustrerar det raka sättet att arbeta med JSON i Ruby, vilket gör det tillgängligt för uppgifter som varierar från enkla datamanipulationer till komplexa API-kommunikationer.
