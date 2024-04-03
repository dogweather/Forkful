---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:12:25.081906-07:00
description: "Assosiatiiviset taulukot, tunnetaan my\xF6s nimell\xE4 hajautustaulut\
  \ tai sanakirjat PowerShelliss\xE4, mahdollistavat tietojen tallentamisen avain-arvo\
  \ -pareina,\u2026"
lastmod: '2024-03-13T22:44:56.773203-06:00'
model: gpt-4-0125-preview
summary: "Assosiatiiviset taulukot, tunnetaan my\xF6s nimell\xE4 hajautustaulut tai\
  \ sanakirjat PowerShelliss\xE4, mahdollistavat tietojen tallentamisen avain-arvo\
  \ -pareina, mik\xE4 tekee tietojen hakemisesta suoraviivaista ja tehokasta."
title: "Assosiatiivisten taulukoiden k\xE4ytt\xF6"
weight: 15
---

## Kuinka:
Assosiatiivisten taulukoiden luominen ja käyttäminen PowerShellissä on melko suoraviivaista. Tässä miten teet taian:

**Assosiatiivisen taulukon luominen:**

```PowerShell
$myAssociativeArray = @{}
$myAssociativeArray["name"] = "Alex"
$myAssociativeArray["age"] = 25
$myAssociativeArray["job"] = "Insinööri"
```

Tämä koodinpätkä luo assosiatiivisen taulukon, jossa on kolme avain-arvo-paria.

**Arvojen hakeminen:**

Saadaksesi arvon, viittaa sen avaimella:

```PowerShell
Write-Output $myAssociativeArray["name"]
```

**Esimerkkitulostus:**

```
Alex
```

**Tietojen lisääminen tai muokkaaminen:**

Käytä vain avainta lisätäksesi uuden parin tai muokataksesi olemassa olevaa:

```PowerShell
$myAssociativeArray["location"] = "New York" # Lisää uuden avain-arvo-parin
$myAssociativeArray["job"] = "Vanhempi Insinööri" # Muokkaa olemassa olevaa paria
```

**Iterointi assosiatiivisessa taulukossa:**

Käy läpi avaimet ja arvot tällä tavalla:

```PowerShell
foreach ($key in $myAssociativeArray.Keys) {
  $value = $myAssociativeArray[$key]
  Write-Output "$key : $value"
}
```

**Esimerkkitulostus:**

```
name : Alex
age : 25
job : Vanhempi Insinööri
location : New York
```

## Syväsukellus
Assosiatiivisten taulukoiden konsepti on yleinen monissa ohjelmointikielissä, yleensä kutsutaan sanakirjaksi, kartaksi tai hajautustauluksi kielen mukaan. PowerShellissä, assosiatiiviset taulukot toteutetaan hajautustauluina, jotka ovat melko tehokkaita avaimien hakemisessa, tietojen tallentamisessa ja yksilöllisten avainten kokoelman ylläpitämisessä.

Historiallisesti assosiatiiviset taulukot tarjoavat keinon hallita objektikokoelmia, joista jokainen nimike voidaan nopeasti hakea ilman kokoelman läpikäymistä, käyttäen sen avainta. Tietojen hakemisen ja muokkaamisen tehokkuus assosiatiivisissa taulukoissa tekee niistä suositun valinnan monenlaisiin tehtäviin. Niillä on kuitenkin rajoituksia, kuten järjestyksen ylläpitäminen, jossa järjestetyt sanakirjat tai mukautetut objektit voivat olla parempi vaihtoehto.

Huolimatta rajoituksistaan, assosiatiiviset taulukot/hajautustaulut PowerShellissä ovat uskomattoman joustavia ja tehokas työkalu skriptauksessa. Ne mahdollistavat dynaamisen tietojen tallentamisen ja ovat erityisen hyödyllisiä konfiguraatioissa, tietojen käsittelyssä ja missä tahansa rakenteellista tietomuotoa tarvitaan ilman muodollisen luokkamäärittelyn ylikuormitusta. Muista vain, vaikka assosiatiiviset taulukot ovat täydellisiä avainpohjaiseen hakemiseen, jos tehtäväsi sisältää monimutkaisia tietorakenteita tai vaatii tietyn järjestyksen ylläpitoa, saatat haluta tutkia muita tietotyyppejä tai mukautettuja objekteja PowerShellissä.
