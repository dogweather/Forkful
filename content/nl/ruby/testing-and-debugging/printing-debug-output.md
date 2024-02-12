---
title:                "Debug-output afdrukken"
aliases:
- /nl/ruby/printing-debug-output/
date:                  2024-01-28T22:04:24.725390-07:00
model:                 gpt-4-0125-preview
simple_title:         "Debug-output afdrukken"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/ruby/printing-debug-output.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Debug-output printen in Ruby is als broodkruimels achterlaten in je code om variabele waarden en programmaduur bij te houden. Programmeurs doen dit om bugs te vangen door te controleren wat hun code op verschillende momenten doet.

## Hoe te:
In Ruby zijn `puts` en `p` je methoden voor snelle output naar de console.

```Ruby
def wie_zei_wat
  citaat = "Zijn of niet zijn"
  auteur = "Shakespeare"
  puts "Citaat: #{citaat}"
  p "Gezegd door: #{auteur}"
end

wie_zei_wat
```

Voorbeelduitvoer:

```
Citaat: Zijn of niet zijn
"Gezegd door: Shakespeare"
```

De `puts` methode print een voor mensen leesbare output, met een nieuwe regel aan het einde. Daartegenover print `p` de waarde in een ruwere vorm, nuttig wanneer je moet zien of iets een string is of niet.

## Diepere duik
Voordat er fancy IDE's waren, was printen naar de console het debuggen. Het is een oude maar gouden techniek, vooral wanneer je de overhead van het opzetten van een debugger wilt vermijden.

Als alternatieven kun je `pp` gebruiken voor het pretty-printen van complexe objecten, of gem-bibliotheken zoals `awesome_print` voor verbeterde leesbaarheid. Als je debug-output te spraakzaam wordt, overweeg dan een logbibliotheek om de niveaus van spraakzaamheid te beheersen.

Implementatiegewijs schrijven `puts` en `p` naar `$stdout`, een wereldwijde I/O-stream in Ruby. Output kan indien nodig worden omgeleid. Onthoud, hoewel deze methoden handig zijn, kunnen excessieve debug-prints je console vervuilen en het debuggen moeilijker maken.

## Zie ook
- Ruby-documentatie voor `Kernel#puts`: https://ruby-doc.org/core/Kernel.html#method-i-puts
- Ruby-documentatie voor `Kernel#p`: https://ruby-doc.org/core/Kernel.html#method-i-p
- Een handleiding voor pretty printen in Ruby: https://ruby-doc.org/stdlib/libdoc/pp/rdoc/PP.html
- De Awesome Print gem voor fancy output: https://rubygems.org/gems/awesome_print/
