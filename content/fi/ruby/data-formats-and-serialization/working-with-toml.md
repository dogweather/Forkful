---
title:                "Työskentely TOML:n kanssa"
aliases:
- fi/ruby/working-with-toml.md
date:                  2024-01-26T04:26:00.594768-07:00
model:                 gpt-4-0125-preview
simple_title:         "Työskentely TOML:n kanssa"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/ruby/working-with-toml.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?

TOML on konfiguraatiotiedostomuoto, joka on helppo lukea sen selkeiden semantiikkojen ansiosta. Ohjelmoijat käyttävät TOML:ää sovellusten konfiguraatioiden hallintaan ja datan sarjallistamiseen ilman XML:n raskautta tai YAML:n oikkuja.

## Kuinka:

Asenna ensin `toml-rb`-gem. Se on suosittu valinta TOML-jäsentämiseen Rubylla.

```Ruby
gem install toml-rb
```

Seuraavaksi, TOML-tiedoston lukeminen:

```Ruby
require 'toml-rb'

toml_sisältö = File.read('config.toml')
konfiguraatio = TomlRB.parse(toml_sisältö)
puts konfiguraatio['title']
```

Näyteulostus voisi olla:

```
My Awesome App
```

Kirjoittaminen TOML-tiedostoon:

```Ruby
require 'toml-rb'

konfiguraatio = {
  'title' => 'My Awesome App',
  'owner' => {
    'name' => 'John Doe',
    'dob' => Date.new(1979, 5, 27)
  }
}

toml_merkkijono = TomlRB.dump(konfiguraatio)
File.write('config.toml', toml_merkkijono)
```

Tarkista `config.toml`, ja näet asetuksesi, siististi tallennettuina.

## Syväluotaus

TOML, joka tarkoittaa Tom's Obvious, Minimal Language, luotiin Tom Preston-Wernerin, GitHubin perustajajäsenen, toimesta vuonna 2013. Sen päämääränä on olla suoraviivainen formaatti, joka on helppo jäsentää datarakenteiksi. Vaikka JSON on loistava API:eille ja YAML on joustava, TOML:n erikoisala on sen ihmiskeskeisyys. Toisin kuin YAML, joka voi olla tarkka sisennyksistä, TOML pyrkii INI-tyyppiseen rakenteeseen, jonka monet kokevat yksinkertaisemmaksi ja vähemmän virhealttiiksi.

Vaihtoehtoja kuten JSON, YAML tai XML, kullakin on omat vahvuutensa, mutta TOML kukoistaa skenaarioissa, joissa konfiguraatio tulisi olla helposti ylläpidettävissä sekä ihmisille että ohjelmille. Se ei ole vain yksinkertaisempi, vaan myös vaatii tiukkaa ja luettavaa muotoilua.

Teknisellä puolella, TOML-sisällön jäsentämiseen Rubylla hyödynnetään gemit kuten `toml-rb`. Tämä gem hyödyntää Rubyn dynaamista luonnetta, muuntaen TOML-datat suoraan Rubyn natiiveihin hash-tauluihin, taulukkoihin ja muihin perustietorakenteisiin. Tämä muunnos tarkoittaa, että kehittäjät voivat työskennellä TOML-datan kanssa tuttujen Rubyn semantiikkojen ja metodien avulla.

## Katso Myös

- TOML-projekti ja spesifikaatio: https://toml.io/en/
- `toml-rb` gem: https://github.com/emancu/toml-rb
- TOML:n, YAML:n ja JSON:n vertailu: https://blog.theodo.com/2021/08/compare-yml-toml-json/
