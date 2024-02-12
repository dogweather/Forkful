---
title:                "Satunnaislukujen generointi"
aliases:
- /fi/swift/generating-random-numbers/
date:                  2024-01-27T20:35:24.712662-07:00
model:                 gpt-4-0125-preview
simple_title:         "Satunnaislukujen generointi"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/swift/generating-random-numbers.md"
---

{{< edit_this_page >}}

## Mikä ja miksi?

Satunnaislukujen tuottaminen ohjelmoinnissa tarkoittaa epädeterminististen tai ennustamattomien numeeristen arvojen luomista. Ohjelmoijat käyttävät satunnaislukuja monista syistä, kuten epäennustettavuuden simuloimiseksi peleissä, satunnaisotosten valitsemiseksi tietoaineistoista tai kryptografisiin tarkoituksiin.

## Kuinka:

Swift tarjoaa suoraviivaisen tavan satunnaislukujen tuottamiseen sen standardikirjaston kautta. Näin teet sen eri numeerisille tyypeille:

```Swift
// Arvo satunnainen kokonaisluku välillä 0 ja Int.max
let randomInt = Int.random(in: 0...Int.max)
print(randomInt)

// Arvo satunnainen liukulukuarvo välillä 0.0 ja 1.0
let randomDouble = Double.random(in: 0.0...1.0)
print(randomDouble)

// Arvo satunnainen Bool-arvo
let randomBool = Bool.random()
print(randomBool)
```

Esimerkkitulokset voivat vaihdella, koska, noh, käsittelemmehän kuitenkin satunnaisuutta. Koodin suorittaminen useita kertoja tuottaa erilaisia numeroita ja Boolean-arvoja.

## Syväluotaus

Swiftin lähestymistapa satunnaislukujen tuottamiseen pohjautuu vankkaan ja tehokkaaseen pseudosatunnaislukugeneraattoriin (PRNG). Ennen Swift 4.2:ta kehittäjät turvautuivat ulkopuolisiin kirjastoihin tai taustalla olevan alustan ominaisuuksiin, mikä saattoi johtaa epäjohdonmukaisuuksiin eri alustoilla ja ympäristöissä. Natiivien API:den käyttöönoton myötä Swift 4.2:ssa satunnaislukujen tuottaminen muuttui sekä yksinkertaisemmaksi että johdonmukaisemmaksi, käytetystä alustasta riippumatta.

On kuitenkin tärkeää ymmärtää, että Swiftin standardi satunnaislukugeneraattori ei sovi kryptografisiin tarkoituksiin. Kryptografiaan kehittäjien tulisi käyttää `Security`-kehyksen (framework) tarjoamaa kryptografisesti turvallista satunnaista bittijonoa Apple-alustoilla. Viimeisimmän päivitykseni mukaan Swift ei sisällä alustojen välistä kryptografista satunnaislukugeneraattoria sen standardikirjastossa, mikä ajaa kehittäjiä etsimään kolmannen osapuolen kirjastoja tällaisiin tarpeisiin ei-Apple-alustoilla.

Tieteellisessä laskennassa tai tilanteissa, joissa tarvitaan determinististä pseudosatunnaislukujen sekvenssiä (jolloin sekvenssi voidaan toistaa tarkasti), Swiftin satunnaislukujen tuottaminen ei ehkä ole paras vaihtoehto ilman mahdollisuutta alustaa generaattoria. Tällaisissa tapauksissa erikoiskirjastoja ja algoritmeja käytetään usein näiden tarkkojen vaatimusten täyttämiseen.
