---
date: 2024-01-20 17:35:46.546659-07:00
description: "Stringien yhdistely eli konkatenointi tarkoittaa tekstijonojen liitt\xE4\
  mist\xE4 yhteen. Sit\xE4 k\xE4ytet\xE4\xE4n, koska usein haluat muodostaa dynaamisia\
  \ tekstej\xE4, kuten\u2026"
lastmod: '2024-03-13T22:44:56.647830-06:00'
model: gpt-4-1106-preview
summary: "Stringien yhdistely eli konkatenointi tarkoittaa tekstijonojen liitt\xE4\
  mist\xE4 yhteen."
title: "Merkkijonojen yhdist\xE4minen"
weight: 3
---

## How to: (Miten:)
```PHP
<?php
// Yhdistetään kaksi merkkijonoa käyttämällä '.'-operaattoria
$tervehdys = "Hei, " . "maailma!";
echo $tervehdys; // Outputs: Hei, maailma!

// Yhdistetään dynaamisesti käyttäen muuttujia
$nimi = "Jorma";
$viesti = "Tervetuloa, " . $nimi . "!";
echo $viesti; // Outputs: Tervetuloa, Jorma!

// Yhdistelmän luominen ja tulostaminen samassa komennossa
echo "Yksi " . "kaksi " . "kolme"; // Outputs: Yksi kaksi kolme
?>
```

## Deep Dive (Syväsukellus):
Ennen PHP:n versiota 4, yleisin tapa yhdistää merkkijonoja oli käyttää `,`-operaattoria, mutta se korvattiin `.`-operaattorilla selkeyden ja suorituskyvyn parantamiseksi. Vaihtoehtoina on syntaksit, kuten kaksoispisteet merkkijonojen ympärillä, jotka arvioivat muuttujat suoraan merkkijonon sisällä, tai `sprintf()`-funktio, joka tarjoaa enemmän muotoiluosuuksia ja on hyödyllinen monimutkaisissa yhdistelyissä. Suorituskyvyn näkökulmasta yhdisteltäessä suuria merkkijonoja, `implode()`-funktio voi olla tehokkaampi, erityisesti, kun käytössä on merkkijonojen lista tai taulukko.

## See Also (Katso Myös):
- PHP:n virallinen dokumentaatio merkkijonoista: [php.net/manual/en/language.types.string.php](https://www.php.net/manual/en/language.types.string.php)
- Hyvät käytännöt merkkijonojen käsittelyyn: [phptherightway.com/#strings](https://phptherightway.com/#strings)
- `sprintf()`-funktion käyttö: [php.net/manual/en/function.sprintf.php](https://www.php.net/manual/en/function.sprintf.php)
