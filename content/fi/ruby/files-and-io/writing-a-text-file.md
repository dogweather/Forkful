---
aliases:
- /fi/ruby/writing-a-text-file/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:29:03.851304-07:00
description: "Tekstitiedostoon kirjoittaminen Rubylla on perustoiminto, jonka avulla\
  \ voit tallentaa tulosteita ja tietoja pysyv\xE4sti, mahdollistaen datan my\xF6\
  hemp\xE4\xE4\u2026"
lastmod: 2024-02-18 23:09:08.202809
model: gpt-4-0125-preview
summary: "Tekstitiedostoon kirjoittaminen Rubylla on perustoiminto, jonka avulla voit\
  \ tallentaa tulosteita ja tietoja pysyv\xE4sti, mahdollistaen datan my\xF6hemp\xE4\
  \xE4\u2026"
title: Tekstitiedoston kirjoittaminen
---

{{< edit_this_page >}}

## Mikä ja Miksi?
Tekstitiedostoon kirjoittaminen Rubylla on perustoiminto, jonka avulla voit tallentaa tulosteita ja tietoja pysyvästi, mahdollistaen datan myöhempää pääsyä tai muokkausta varten. Ohjelmoijat suorittavat tätä tehtävää usein syistä kuten lokitiedostojen kirjoittaminen, asetusten tallentaminen tai datan vieminen ihmisen luettavassa muodossa.

## Miten:
Ruby tekee tiedosto-operaatioista suoraviivaisia. Tiedostoon kirjoittamiseen voit käyttää Rubyn sisäänrakennettua `File`-luokkaa. Seuraava esimerkki näyttää, miten tiedosto avataan kirjoitusta (`"w"`-tila) ja lisäystä (`"a"`-tila) varten, sitten kirjoitetaan merkkijono siihen, ja varmistetaan, että tiedosto suljetaan jälkeenpäin:

```ruby
# Uuden sisällön kirjoittaminen tiedostoon, olemassa olevan sisällön ylikirjoittaminen
File.open("example.txt", "w") do |file|
  file.puts "Hei, Ruby!"
end

# Sisällön lisääminen tiedoston loppuun
File.open("example.txt", "a") do |file|
  file.puts "Lisää toinen rivi."
end
```
Molempien pätkien ajamisen jälkeen `example.txt`-tiedoston sisältö on:
```
Hei, Ruby!
Lisää toinen rivi.
```

### Kolmannen osapuolen kirjaston käyttö: FileUtils
Monimutkaisempia tiedosto-operaatioita varten Ruby-standardikirjasto `FileUtils` voi tulla tarpeeseen, vaikkakin perustason tiedostonkirjoitukseen standardi `File`-metodit riittävät. Kuitenkin, jos haluat kopioita, siirtää, poistaa tai suorittaa muita tiedostojärjestelmäoperaatioita tiedostonkirjoituksen yhteydessä, `FileUtils` on tutkimisen arvoinen.

Esimerkki `FileUtils`in käytöstä hakemiston luomiseen ja sitten tiedostoon kirjoittamiseen kyseisessä hakemistossa:
```ruby
require 'fileutils'

FileUtils.mkdir_p 'logs'
File.open("logs/today.log", "w") do |file|
  file.puts "Lokimerkintä: #{Time.now}"
end
```

Tämä osoittaa uuden hakemiston `logs` luomisen, jos sitä ei jo ole olemassa, ja uuteen tiedostoon `today.log` kirjoittamisen siinä, esitellen sekä hakemiston että tiedoston käsittelyä suoraan kirjoittamatta FileUtilsilla, mutta hyödyntäen sen hakemistonkäsittelykykyä.
