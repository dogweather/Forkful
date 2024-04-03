---
date: 2024-01-20 17:38:31.722334-07:00
description: "Mit\xE4 ja Miksi? K\xE4\xE4nt\xE4minen merkkijono pieniksi kirjaimiksi\
  \ tarkoittaa kaikkien kirjainten muuttamista niiden pienikokoisiksi vastineiksi.\
  \ Ohjelmoijat\u2026"
lastmod: '2024-03-13T22:44:56.979274-06:00'
model: gpt-4-1106-preview
summary: "Mit\xE4 ja Miksi."
title: Merkkijonon muuntaminen pieniksi kirjaimiksi
weight: 4
---

## How to:
Kuinka? Fish Shellillä saat merkkijonon pieniksi kirjaimiksi `string lower`-komennolla. Helppoa ja suoraviivaista. Kokeile itse:

```Fish Shell
echo "Tässä On Isolla Alkavia" | string lower
```

Tulostus:

```Fish Shell
tässä on isolla alkavia
```

## Deep Dive
Syväsukellus: Alun perin UNIX-komentotulkit, kuten Bourne shell, eivät tukeneet merkkijonojen käsittelyä suoraan. Fish Shell toi kehittyneet merkkijono-ominaisuudet shellien käyttöön. Vaihtoehtoisia keinoja merkkijonojen pienentämiseen ovat `awk`, `tr`, `sed`, mutta Fishissä `string`-työkalu hoitaa tämän tyylikkäästi. Fish Shell käyttää Unicode-määritelmiä isot-pienet kirjainmuunnoksille, joten esimerkiksi diakriittiset merkit käännetään oikein.

## See Also
Lisätietoja: Tutustu Fish Shell:n dokumentaatioon ja muiden työkalujen käyttöohjeisiin syvällisemmän ymmärryksen saavuttamiseksi.

- [Fish Shell Documentation](https://fishshell.com/docs/current/index.html#string)
- [AWK Manual](https://www.gnu.org/software/gawk/manual/gawk.html)
- [GNU `tr` Manual](https://www.gnu.org/software/coreutils/manual/html_node/tr-invocation.html)
- [SED Manual](https://www.gnu.org/software/sed/manual/sed.html)
