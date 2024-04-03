---
date: 2024-01-20 17:53:43.015528-07:00
description: "Luetaan tekstifailia, koska tarvitaan dataa siit\xE4. Se on olennaista,\
  \ kun k\xE4sitell\xE4\xE4n asetuksia, k\xE4ytt\xE4j\xE4n sis\xE4lt\xF6\xE4 tai skriptej\xE4\
  ."
lastmod: '2024-03-13T22:44:56.756218-06:00'
model: gpt-4-1106-preview
summary: "Luetaan tekstifailia, koska tarvitaan dataa siit\xE4."
title: Tekstitiedoston lukeminen
weight: 22
---

## Näin teet:
```Bash
# Failin lukeminen rivi riviltä
while IFS= read -r line; do
    echo "$line"
done < "esimerkki.txt"

# Tailin hyödyntäminen viimeisen rivin näyttämiseen
tail -n 1 esimerkki.txt

# Awk:n käyttö tietyn kolumnin tulostamiseen
awk '{print $2}' esimerkki.txt
```

Esimerkki ulostulosta:
```
Tämä on ensimmäinen rivi.
Tämä on toinen rivi.
```

## Syväsukellus
Aikanaan tekstitiedostojen luku oli yksinkertaista, koska datan formaatit olivat perustietoja. Nykyään on paljon vaihtoehtoja: `cat`, `head`, `tail`, `less`, `more`, `awk`, `sed`. Bashissa tiedoston lukeminen perustuu yleensä striimeihin ja putkien käyttöön datan siirtämiseen. Tehokkuus ja työkalujen soveltuvuus datan määrään ja formaattiin kannattaa ottaa huomioon.

## Katso myös
- GNU Coreutils: https://www.gnu.org/software/coreutils/
- Bash-hakemisto: http://tldp.org/LDP/abs/html/
- Advanced Bash-Scripting Guide: https://www.tldp.org/LDP/abs/html/
