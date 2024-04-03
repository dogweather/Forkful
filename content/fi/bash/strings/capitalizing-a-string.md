---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:59.073670-07:00
description: "Merkkijonon alkukirjaimen muuttaminen isoksi Bashissa tarkoittaa merkkijonon\
  \ ensimm\xE4isen merkin muuttamista isoksi kirjaimeksi, samalla kun loput\u2026"
lastmod: '2024-03-13T22:44:56.721776-06:00'
model: gpt-4-0125-preview
summary: "Merkkijonon alkukirjaimen muuttaminen isoksi Bashissa tarkoittaa merkkijonon\
  \ ensimm\xE4isen merkin muuttamista isoksi kirjaimeksi, samalla kun loput merkkijonosta\
  \ j\xE4tet\xE4\xE4n muuttumattomiksi."
title: Merkkijonon muuttaminen isoiksi kirjaimiksi
weight: 2
---

## Kuinka:
Bash ei sisällä erityistä sisäänrakennettua toimintoa merkkijonojen alkukirjaimen muuttamiseen isoksi, mutta tämän tehtävän voi suorittaa käyttämällä parametrilaajennusta tai ulkoisia työkaluja, kuten `awk`. Tässä on muutama tapa muuttaa merkkijonon ensimmäinen kirjain isoksi Bashissa:

**Käyttämällä parametrilaajennusta:**

Tämä menetelmä manipuloi merkkijonoa suoraan kuorella.

```bash
str="hello world"
capitalized="${str^}"
echo "$capitalized"
```
Tuloste:
```
Hello world
```

**Käyttämällä `awk`:**

`awk` on tehokas tekstinkäsittelytyökalu, joka on saatavilla useimmissa Unix-tyyppisissä käyttöjärjestelmissä, ja sitä voidaan hyödyntää merkkijonojen alkukirjaimen muuttamisessa isoksi.

```bash
str="hello world"
echo "$str" | awk '{print toupper(substr($0, 1, 1)) tolower(substr($0, 2))}'
```
Tuloste:
```
Hello world
```

**Käyttämällä `sed`:**

Perinteisempään lähestymistapaan voidaan käyttää `sed`-työkalua merkkijonon ensimmäisen kirjaimen muuttamiseen isoksi. Tämä menetelmä on kuitenkin hieman monimutkaisempi verrattuna edellä mainittuihin menetelmiin.

```bash
str="hello world"
echo "$str" | sed 's/./\u&/'
```
Tuloste:
```
Hello world
```

Nämä katkelmat osoittavat, miten Bashissa voidaan muuttaa merkkijonon ensimmäinen kirjain isoksi, korostaen kuoriskriptauksen joustavuutta tekstiä manipuloitaessa.
