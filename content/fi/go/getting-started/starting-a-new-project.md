---
aliases:
- /fi/go/starting-a-new-project/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:09:46.286154-07:00
description: "Uuden projektin aloittaminen Go:ssa sis\xE4lt\xE4\xE4 ty\xF6tilan pystytt\xE4\
  misen ja sen alustamisen tarvittavilla Go-moduuleilla. Ohjelmoijat tekev\xE4t t\xE4\
  m\xE4n koodin\u2026"
lastmod: 2024-02-18 23:09:07.085751
model: gpt-4-0125-preview
summary: "Uuden projektin aloittaminen Go:ssa sis\xE4lt\xE4\xE4 ty\xF6tilan pystytt\xE4\
  misen ja sen alustamisen tarvittavilla Go-moduuleilla. Ohjelmoijat tekev\xE4t t\xE4\
  m\xE4n koodin\u2026"
title: Uuden projektin aloittaminen
---

{{< edit_this_page >}}

## Mikä & Miksi?

Uuden projektin aloittaminen Go:ssa sisältää työtilan pystyttämisen ja sen alustamisen tarvittavilla Go-moduuleilla. Ohjelmoijat tekevät tämän koodin organisoinnin, riippuvuuksien hallinnan tehostamisen ja rakennusprosessien helpottamisen vuoksi. Se on perustavanlaatuista skaalautuvan ja ylläpidettävän ohjelmiston luomiseen Go:ssa.

## Kuinka:

Aloita varmistamalla, että Go on asennettu suorittamalla `go version` komentorivillä. Sinun pitäisi nähdä asentamasi Go-version tulosteena. Seuraavaksi, aloitetaan uusi projekti. Siirry työtilaasi ja suorita:

```shell
mkdir hello-world
cd hello-world
```

Tämä luo uuden hakemiston projektillesi ja siirtää sinut siihen. Nyt, alusta moduuli:

```shell
go mod init example.com/hello-world
```

Korvaa `example.com/hello-world` omalla moduulipolullasi. Tämä komento luo `go.mod` tiedoston hakemistoosi, ilmoittaen uuden Go-moduulin aloituksesta. Tältä `go.mod` voi näyttää:

```plaintext
module example.com/hello-world

go 1.18
```

`go.mod` seuraa projektisi riippuvuuksia. Nyt, luo `main.go` tiedosto:

```shell
touch main.go
```

Avaa `main.go` suosikkieditorissasi ja lisää seuraava koodi tulostamaan "Hello, World!":

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

Suorittaaksesi ohjelmasi, palaa takaisin komentoriville ja suorita:

```shell
go run main.go
```

Sinun pitäisi nähdä:

```plaintext
Hello, World!
```

Onnittelut! Olet juuri aloittanut uuden Go-projektin ja suorittanut ensimmäisen Go-ohjelmasi.

## Syväsukellus

Aloitteen tuoda moduulit Go:n riippuvuuksien hallinnan standardiksi oli merkittävä muutos Go-ekosysteemissä, virallisesti omaksuttu Go 1.11:ssä. Ennen moduuleja Go-kehittäjät turvautuivat GOPATH-ympäristömuuttujaan riippuvuuksien hallintaan, mikä oli vähemmän intuitiivista ja usein johti kuuluisaan "riippuvuushelvettiin".

Moduulit tarjoavat kapseloidun tavan hallita projektiriippuvuuksia, versionhallintaa ja ovat siirtymä kohti Go-projekteja, jotka ovat enemmän itsenäisiä ja siirrettäviä. Jokainen moduuli määrittelee riippuvuutensa, jotka Go seuraa `go.mod` tiedostossa, yksinkertaistaen riippuvuuksien hallintaa eri ympäristöissä ja kehitysvaiheissa.

On kuitenkin huomionarvoista, että vaikka Go-moduulit ovat nyt standardi, jotkut perintöprojektit saattavat silti käyttää GOPATHia. Useimmille uusille projekteille moduulit tarjoavat yksinkertaisemman ja tehokkaamman hallintajärjestelmän, mutta GOPATHin ymmärtäminen voi olla kätevää vanhempien Go-koodikantojen ylläpitämiseen tai niihin panostamiseen.

Vaihtoehtojen osalta, vaikka Go-moduulit ovat nyt de facto standardi, Go-yhteisö on kokeillut aiemmin muita riippuvuuksien hallintatyökaluja, kuten `dep`. Kuitenkin, nämä on suurelta osin syrjäytetty virallisen moduulituen myötä, joka on integroitu Go-työkaluketjuun.
