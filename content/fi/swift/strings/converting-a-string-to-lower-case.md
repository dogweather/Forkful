---
date: 2024-01-20 17:39:08.554349-07:00
description: "Tekstin muuttaminen pieniksi kirjaimiksi tarkoittaa kaikkien merkkijonon\
  \ kirjainten muuntamista vastaaviksi pienaakkosiksi. T\xE4t\xE4 tehd\xE4\xE4n yhten\xE4\
  ist\xE4m\xE4\xE4n\u2026"
lastmod: '2024-03-13T22:44:56.894616-06:00'
model: gpt-4-1106-preview
summary: Tekstin muuttaminen pieniksi kirjaimiksi tarkoittaa kaikkien merkkijonon
  kirjainten muuntamista vastaaviksi pienaakkosiksi.
title: Merkkijonon muuntaminen pieniksi kirjaimiksi
weight: 4
---

## How to:
Swiftissä merkkijonon muuttaminen pieniksi kirjaimiksi on yksinkertaista. Käytä `lowercased()` metodia:

```Swift
let originalString = "Hei Maailma!"
let lowercasedString = originalString.lowercased()
print(lowercasedString)
```

Tulostuu: `hei maailma!`

## Deep Dive
Alkuperäisen Swift 1:ssä (2014), `.lowercaseString` oli tapa muuttaa merkkijonot pieniksi kirjaimiksi. Swift 3:ssa (2016) se muutettiin `.lowercased()` metodiksi, joka on ollut käytössä siitä lähtien. Alternatiiveja suoraan `.lowercased()` metodille ei ole, mutta voi olla tilanteita, joissa halutaan esimerkiksi säilyttää tietyt merkit sellaisinaan tai soveltaa kulttuurisensitiivistä pienten kirjaimien käyttöä, missä tarvitaan lisälogiikkaa. Swift tekee pienentämisen Unicode-standardin mukaisesti, joten se käsittelee laajan valikoiman kirjaimia eri kielistä.

## See Also
- Swiftin virallinen dokumentaatio merkkijonon käsittelyyn: [Swift String and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
- Unicode-standardi: [Unicode Character Database](https://www.unicode.org/ucd/)
