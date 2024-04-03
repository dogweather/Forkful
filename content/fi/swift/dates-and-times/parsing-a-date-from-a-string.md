---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:15:41.316934-07:00
description: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sent\xE4minen merkkijonosta k\xE4sitt\xE4\
  \xE4 tekstuaalisten p\xE4iv\xE4m\xE4\xE4r\xE4- ja aikamuotojen muuntamisen `Date`-olioksi.\
  \ T\xE4m\xE4 prosessi on olennainen\u2026"
lastmod: '2024-03-13T22:44:56.915933-06:00'
model: gpt-4-0125-preview
summary: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sent\xE4minen merkkijonosta k\xE4sitt\xE4\
  \xE4 tekstuaalisten p\xE4iv\xE4m\xE4\xE4r\xE4- ja aikamuotojen muuntamisen `Date`-olioksi."
title: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sennys merkkijonosta"
weight: 30
---

## Kuinka:


### Käyttäen Foundationin `DateFormatter`ia
Swiftin vakio kirjasto, Foundation, tarjoaa `DateFormatter`in merkkijonojen muuntamiseen `Date`-olioiksi ja päinvastoin. Päivämäärän jäsentämiseksi merkkijonosta määrität merkkijonoon sopivan päivämäärämuodon ja käytät sitten muotoilijaa sen jäsentämiseen.

```swift
import Foundation

let dateString = "2023-04-30"
let formatter = DateFormatter()
formatter.dateFormat = "yyyy-MM-dd"
if let date = formatter.date(from: dateString) {
    print("Jäsennetty päivämäärä: \(date)")
} else {
    print("Päivämäärän jäsentäminen epäonnistui")
}
// Esimerkkituloste: Jäsennetty päivämäärä: 2023-04-29 22:00:00 +0000
```

Huomaa, että tuloste voi vaihdella aikavyöhykkeesi mukaan.

### Käyttäen `ISO8601DateFormatter`ia
ISO 8601 päivämäärämuodoille Swift tarjoaa erikoistuneen muotoilijan, `ISO8601DateFormatter`in, joka yksinkertaistaa jäsentämisprosessia.

```swift
import Foundation

let dateString = "2023-04-30T15:00:00+00:00"
let isoFormatter = ISO8601DateFormatter()
if let date = isoFormatter.date(from: dateString) {
    print("Jäsennetty ISO8601 päivämäärä: \(date)")
} else {
    print("ISO8601 päivämäärän jäsentäminen epäonnistui")
}
// Esimerkkituloste: Jäsennetty ISO8601 päivämäärä: 2023-04-30 15:00:00 +0000
```

### Käyttäen kolmannen osapuolen kirjastoa: SwiftDate
Vaikka Swift tarjoaa vankkoja työkaluja päivämäärän jäsentämiseen, kolmannen osapuolen kirjastot kuten SwiftDate tarjoavat vielä enemmän joustavuutta ja mukavuutta. Lisättyäsi SwiftDaten projektiisi, jäsentäminen muuttuu yksinkertaiseksi:

```swift
import SwiftDate

let dateString = "huhtikuu 30, 2023"
if let date = dateString.toDate("MMMM dd, yyyy") {
    print("Jäsennetty päivämäärä SwiftDaten avulla: \(date)")
} else {
    print("Päivämäärän jäsentäminen SwiftDaten avulla epäonnistui")
}
// Esimerkkituloste: Jäsennetty päivämäärä SwiftDaten avulla: 2023-04-30 00:00:00 +0000
```

SwiftDate yksinkertaistaa jäsentämistä luonnollisen kielen ja laajan päivämäärämuotojen valikoiman avulla, tehden siitä voimakkaan lisäyksen Swift-ohjelmointityökalupakkiisi.
