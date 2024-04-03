---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:56.779644-07:00
description: "Merkkijonon alkukirjaimen muuttaminen isoksi tarkoittaa merkkijonon\
  \ ensimm\xE4isen kirjaimen muuttamista isoksi kirjaimeksi samalla varmistaen, ett\xE4\
  \ kaikki\u2026"
lastmod: '2024-03-13T22:44:56.209464-06:00'
model: gpt-4-0125-preview
summary: "Merkkijonon alkukirjaimen muuttaminen isoksi tarkoittaa merkkijonon ensimm\xE4\
  isen kirjaimen muuttamista isoksi kirjaimeksi samalla varmistaen, ett\xE4 kaikki\
  \ muut kirjaimet ovat pieni\xE4."
title: Merkkijonon muuttaminen isoiksi kirjaimiksi
weight: 2
---

## Kuinka:
Elixir tarjoaa suoraviivaisen tavan muuttaa merkkijonot alkukirjaimeltaan isoksi käyttämällä sen sisäänrakennettuja funktioita ilman kolmansien osapuolien kirjastoja. Tässä on yksinkertainen esimerkki:

```elixir
string = "elixir ohjelmointi"
capitalized_string = String.capitalize(string)
IO.puts capitalized_string
```

Tuloste:

```
Elixir ohjelmointi
```

Tapauksissa, joissa tarvitaan enemmän kontrollia tai monimutkaisempaa alkukirjainten muokkauslogiikkaa, saatat yhdistää erilaisia String-funktioita. Esimerkiksi, jos haluat muuttaa jokaisen sanan alkukirjaimen isoksi lauseessa, voit jakaa lauseen sanoiksi, muuttaa jokaisen alkukirjaimen isoksi ja sitten yhdistää ne takaisin yhteen:

```elixir
sentence = "elixir on hauskaa"
capitalized_sentence = sentence 
                        |> String.split() 
                        |> Enum.map(&String.capitalize/1) 
                        |> Enum.join(" ")

IO.puts capitalized_sentence
```

Tuloste:

```
Elixir On Hauskaa
```

Vaikka Elixiring peruskirjasto kattaa useimmat tarpeet, tarkempaan tekstin käsittelyyn, mukaan lukien edistyneet merkkijonojen alkukirjaimen muokkaukset, saatat tutkia kolmannen osapuolen kirjastoja, kuten Cldr kansainvälistämistä varten, joka voi tarjota paikkakohtaisia alkukirjaimen muokkauskäyttäytymisiä.
