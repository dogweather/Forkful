---
title:                "Merkkijonon muuntaminen pieniksi kirjaimiksi"
date:                  2024-01-20T17:39:01.554231-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonon muuntaminen pieniksi kirjaimiksi"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/ruby/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why?
Muutetaan merkkijonot pieniksi kirjaimiksi. Tämä on hyödyllistä kun haluamme vertailla tekstejä riippumatta kirjainkoosta tai yhdenmukaistaa tietoja.

## How to:
```Ruby
# Ennen alkuun pääsyä - varmista, että olet asentanut uusimman version Rubysta.
# String-olioon pienennys Rubyssa:
esimerkki = "Tämä On Ruby Esimerkki!"
puts esimerkki.downcase
# Tulostaa: "tämä on ruby esimerkki!"
```

## Deep Dive:
String-luokan `downcase`-metodi on ollut Rubyn core-kirjastossa alusta asti. Se muuttaa merkkijonon jokaisen kirjaimen vastaavaksi pienikirjaimiseksi. Historiallisesti tämä on ollut tärkeää, koska tietokoneet erottavat isot ja pienet kirjaimet. Vaihtoehtoina on myös `downcase!`, joka muuttaa alkuperäisen merkkijonon paikan päällä, ja Railsin `squish`, joka poistaa ylimääräiset välilyönnit ja tekee `downcase`. Implementaation yksityiskohdat liittyvät siihen, miten Ruby käsittelee merkkien encodingia, jotta metodi toimii kaikilla eri merkistöillä.

## See Also:
- Ruby-dokumentaatio String#downcase: [ruby-doc.org](https://ruby-doc.org/core-2.7.0/String.html#method-i-downcase)
- Rubyn metaprogrointia ja sen metodeja käsittelevä opas: [https://poignant.guide](https://poignant.guide)
- Ruby Style Guide, jonka avulla koodisi pysyy puhtaana ja ylläpidettävänä: [https://rubystyle.guide](https://rubystyle.guide)