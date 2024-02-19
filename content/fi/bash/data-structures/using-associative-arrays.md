---
aliases:
- /fi/bash/using-associative-arrays/
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:10.785340-07:00
description: "Assosiatiiviset taulukot ovat kuin tehostetut taulukot, jotka mahdollistavat\
  \ merkkijonojen k\xE4ytt\xE4misen indeksein\xE4 pelkkien kokonaislukujen sijaan.\u2026"
lastmod: 2024-02-18 23:09:07.794676
model: gpt-4-0125-preview
summary: "Assosiatiiviset taulukot ovat kuin tehostetut taulukot, jotka mahdollistavat\
  \ merkkijonojen k\xE4ytt\xE4misen indeksein\xE4 pelkkien kokonaislukujen sijaan.\u2026"
title: "Assosiatiivisten taulukoiden k\xE4ytt\xF6"
---

{{< edit_this_page >}}

## Mikä & Miksi?

Assosiatiiviset taulukot ovat kuin tehostetut taulukot, jotka mahdollistavat merkkijonojen käyttämisen indekseinä pelkkien kokonaislukujen sijaan. Ohjelmoijat käyttävät niitä monimutkaisempien tietorakenteiden kanssa, mikä tekee tiedon käsittelystä helpompaa, kun se ei siististi sovi peräkkäiseen luetteloon.

## Kuinka:

Aloita julistamalla Bashissa assosiatiivinen taulukko:

```Bash
declare -A my_array
```

Sen jälkeen voit alkaa täyttää sitä arvoilla käyttäen merkkijonoja avaimina:

```Bash
my_array["name"]="Linux Journal"
my_array["topic"]="Ohjelmointi"
```

Elementtiin pääsee käsiksi käyttämällä sen avainta:

```Bash
echo ${my_array["name"]}  # Tulostaa: Linux Journal
```

Avainten ja arvojen iteroiminen on myös suoraviivaista:

```Bash
for key in "${!my_array[@]}"; do
    echo "$key: ${my_array[$key]}"
done
```

Näytetuloste voisi näyttää tältä:

```
name: Linux Journal
topic: Ohjelmointi
```

Lisätäksesi tai muokataksesi elementtejä, määritä arvo avaimelle samalla tavalla kuin alustavassa täyttämisessä:

```Bash
my_array["lukijat"]="Sinä"
```

Ja elementin poistamiseen käytä `unset`:

```Bash
unset my_array["topic"]
```

## Syväsukellus

Assosiatiiviset taulukot otettiin käyttöön Bashin versiossa 4.0, mikä tekee niistä suhteellisen uuden lisäyksen kieleen. Ennen niiden käyttöönottoa ei-kokonaislukuindeksilla varustettujen taulukoiden käsittely oli hankalaa, usein vaatien kiertotapoja tai ulkoisia työkaluja kuten `awk` tai `sed`.

Pinnan alla Bash toteuttaa assosiatiiviset taulukot hajautustauluja käyttäen. Tämä toteutus mahdollistaa tehokkaan avainhaun, joka pysyy melko vakiona riippumatta taulukon koosta, kriittinen ominaisuus käsikirjoituksen suorituskyvyssä.

Vaikka assosiatiiviset taulukot Bashissa tuovat paljon tehoa ja joustavuutta kuoriskriptaukseen, ne tulevat omien rajoitustensa kanssa, kuten se, että niiden käyttö on hieman kömpelöä verrattuna korkean tason kielien, kuten Pythonin tai JavaScriptin, taulukoihin. Monimutkaisten datan käsittelytehtävien osalta voi silti olla harkitsemisen arvoista käyttää ulkoisia työkaluja tai kieliä, jotka soveltuvat tehtävään paremmin.

Kuitenkin monille tyypillisille skriptaus tehtäville assosiatiiviset taulukot tarjoavat arvokkaan työkalun Bash-ohjelmoijan työkalupakkiin, mahdollistaen luettavampia ja ylläpidettävämpiä skriptejä sallimalla merkityksellisten merkkijonoavainten käytön numeeristen indeksien sijaan.
