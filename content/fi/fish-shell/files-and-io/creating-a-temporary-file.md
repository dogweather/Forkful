---
date: 2024-01-20 17:40:08.928034-07:00
description: "Temp-tiedoston luonti on v\xE4liaikaisten, usein kertak\xE4ytt\xF6isten\
  \ tiedostojen tekemist\xE4. Ohjelmoijat k\xE4ytt\xE4v\xE4t niit\xE4 esimerkiksi\
  \ datan v\xE4liaikaiss\xE4ilytykseen\u2026"
lastmod: '2024-03-13T22:44:57.014428-06:00'
model: gpt-4-1106-preview
summary: "Temp-tiedoston luonti on v\xE4liaikaisten, usein kertak\xE4ytt\xF6isten\
  \ tiedostojen tekemist\xE4."
title: "V\xE4liaikaistiedoston luominen"
weight: 21
---

## How to: (Kuinka tehdä:)
```Fish Shell
# Luo väliaikainen tiedosto
set tmp_file (mktemp)

# Käytä tiedostoa
echo 'Tämä on testi' > $tmp_file

# Tulostetaan väliaikaisen tiedoston sisältö
cat $tmp_file

# Poista väliaikainen tiedosto lopuksi
rm $tmp_file
```

Tulostus näyttäisi tältä:
```
Tämä on testi
```

## Deep Dive (Syväsukellus)
Fish Shell käyttää `mktemp`-ohjelmaa väliaikaisten tiedostojen luontiin. Se on UNIX-standardi ja löytyy useimmista käyttöjärjestelmistä. Vaihtoehtoisesti voitaisiin käyttää `tmpfile()`-funktiota C-ohjelmoinnissa, mutta Fishissä `mktemp` on kätevä ja nopea. Tärkeää on muistaa poistaa temp-tiedostot, etteivät ne täytä levytilaa.

## See Also (Katso Myös)
- Fish Shell Documentation: https://fishshell.com/docs/current/index.html
- UNIX `mktemp` Manual Page: https://man7.org/linux/man-pages/man1/mktemp.1.html
- Bash vs. Fish Shell Differences: https://www.2daygeek.com/bash-vs-fish-shell-differences/
