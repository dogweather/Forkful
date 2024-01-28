---
title:                "XML:n käsittely"
date:                  2024-01-26T04:35:21.127588-07:00
model:                 gpt-4-0125-preview
simple_title:         "XML:n käsittely"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/ruby/working-with-xml.md"
---

{{< edit_this_page >}}

## Mikä ja miksi?
Työskentely XML:n parissa tarkoittaa XML-dokumenttien (eXtensible Markup Language) jäsentämistä, luomista ja manipulointia koodin avulla. Ohjelmoijat tekevät niin kommunikoidakseen monien web-palvelujen, konfiguraatiotiedostojen ja datanvaihtoformaattien kanssa, joissa XML on lingua franca.

## Kuinka:
Käytetään REXML:ää, joka sisältyy Rubyyn, XML-katkelman jäsentämiseen:
```Ruby
require 'rexml/document'
include REXML

xml_data = <<-XML
<fruits>
  <fruit name="apple" color="green"/>
  <fruit name="banana" color="yellow"/>
</fruits>
XML

document = Document.new(xml_data)
document.elements.each('fruits/fruit') do |element|
  puts "Nimi: #{element.attributes['name']}, Väri: #{element.attributes['color']}"
end
```
Tuloste:
```
Nimi: apple, Väri: green
Nimi: banana, Väri: yellow
```

XML:n luominen on myös suoraviivaista:
```Ruby
doc = Document.new
doc.add_element 'fruits'
apple = doc.root.add_element 'fruit', {'name' => 'apple', 'color' => 'green'}
banana = doc.root.add_element 'fruit', {'name' => 'banana', 'color' => 'yellow'}
puts doc
```
XML-tuloste:
```XML
<fruits>
  <fruit name="apple" color="green"/>
  <fruit name="banana" color="yellow"/>
</fruits>
```

## Syvä sukellus:
XML:n juuret juontavat 1990-luvulle yksinkertaistettuna alajoukkona SGML:lle web-dokumentteja varten. Se on verbaliinen mutta erittäin rakenteellinen, ja siksi se on pysynyt mukana. Se ei ole ainoa peli kaupungissa – JSON ja YAML ovat tulleet suosituiksi niiden yksinkertaisuuden vuoksi – mutta XML pitää pintansa monissa yritys- ja perintöjärjestelmissä.

Ruby tarjoaa muutamia tapoja käsitellä XML:ää. REXML on kokonaan Rubylla kirjoitettu kirjasto, joka on helppo ottaa käyttöön. Nokogiri on gem, joka käärii nopeampia C-kirjastoja, tarjoten nopeutta ja lisäominaisuuksia. Valinta niiden välillä? Aloita REXML:llä pienempiin tehtäviin ja siirry Nokogiriin, jos tarvitset enemmän tehoa.

Taustalla XML:n jäsentäminen on merkkijonojen kääntämistä DOM- tai SAX-malleiksi. DOM luo muistiin puun, kun taas SAX virtaa dokumentin läpi ja laukaisee tapahtumia sen jäsentäessä. REXML tarjoaa molemmat mallit, mutta on yleensä hitaampi kuin C-laajennukset, joita Nokogiri käyttää.

## Katso myös:
- Ruby REXML-dokumentaatio: https://www.rubydoc.info/stdlib/rexml
- Nokogiri gem: https://nokogiri.org/
- XML-spesifikaatio: https://www.w3.org/XML/
- Johdatus SAX:iin: https://www.saxproject.org/
- YAML vs. JSON vs. XML vertailu: https://www.upwork.com/resources/json-vs-xml-vs-yaml
