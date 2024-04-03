---
date: 2024-01-26 01:09:07.334748-07:00
description: "Lokitus on sovellusten toimintaa, virheit\xE4 ja muita t\xE4rkeit\xE4\
  \ tietoja tallentavan prosessin kirjaamista pysyv\xE4\xE4n muotoon, kuten tiedostoon\
  \ tai\u2026"
lastmod: '2024-03-13T22:44:56.913148-06:00'
model: gpt-4-1106-preview
summary: "Lokitus on sovellusten toimintaa, virheit\xE4 ja muita t\xE4rkeit\xE4 tietoja\
  \ tallentavan prosessin kirjaamista pysyv\xE4\xE4n muotoon, kuten tiedostoon tai\
  \ tietokantaan."
title: Lokitus
weight: 17
---

## Kuinka:
Swiftissä voit kirjoittaa lokeja konsoliin print-lauseilla tai joustavammalla `os.log`-rajapinnalla, joka kytkeytyy Applen alustoilla käytettävään yhdistettyyn lokitusjärjestelmään (Unified Logging System).

```Swift
import os.log

let logger = OSLog(subsystem: "com.yourapp.domain", category: "network")

func fetchData() {
    // Yksinkertainen print-lause
    print("Hakeminen aloitettu")
    
    // Tietotasoisen tapahtuman lokitus käyttäen os.log:ia
    os_log(.info, log: logger, "Haetaan tietoja API:sta.")
    
    do {
        let data = try performNetworkRequest()
        // Kehitystasoisen tapahtuman lokitus
        os_log(.debug, log: logger, "Data vastaanotettu: %@", data.description)
    } catch {
        // Virhetasoisen tapahtuman lokitus
        os_log(.error, log: logger, "Tietojen haku epäonnistui: %@", error.localizedDescription)
    }
}

func performNetworkRequest() throws -> Data {
    // Simuloidaan verkkopyyntöä
    return Data()
}
```

Esimerkkilokitus konsolissa näyttäisi tältä:

```
Hakeminen aloitettu
Haetaan tietoja API:sta.
Data vastaanotettu: Muutamia databittejä...
```

Virheiden osalta se saattaisi olla:

```
Tietojen haku epäonnistui: Internet-yhteys näyttäisi olevan poissa käytöstä.
```

## Syväsukellus
Lokitus Swiftissä saa uutta tehoa ja tehokkuutta yhdistetyn lokitusjärjestelmän myötä, joka otettiin käyttöön iOS 10:ssä ja macOS Sierrassa. Toisin kuin `print`-lause, joka menee suoraan konsoliin, tämä järjestelmä perustuu aktiviteetteihin ja mahdollistaa lokiviestien suodattamisen niiden tärkeyden ja sen mukaan, ovatko ne kehitys- vai julkaisuversioita.

Historiallinen konteksti kehystää iOS:n ja macOS:n lokituksen kehittymistä alkeellisista print-lauseista kattaviin työkaluihin, jotka integroituvat Instruments-sovelluksen ja konsolin kanssa tarjoten kehittyneitä tapoja analysoida lokia.

Swiftissä on useita vaihtoehtoja lokitukseen, kuten kolmannen osapuolen kirjastot kuten CocoaLumberjack, joka tarjoaa makrokerroksen yhdistetyn lokitusjärjestelmän yläpuolelle. Se tarjoaa parannettua kontrollia lokien muotoiluun, tiedostojen hallintaan ja suorituskykyvaihtoehtoihin.

Lopuksi, toteutuksen yksityiskohdat; OSLog on suunniteltu olemaan tehokas mutta myös yksityisyyttä kunnioittava, kyeten häivyttämään yksityisiä tietoja lokitettaessa. Se luokittelee lokit vakavuus-, virhe-, tiedotus- ja kehitystasoille, tarjoten eri yksityiskohtaisuustasoja ongelmatilanteiden selvittämiseen.

## Katso Myös
- [Applen yhdistetty lokitusdokumentaatio](https://developer.apple.com/documentation/os/logging)
- [Ray Wenderlichin lokitusopas Swiftille ja OSLogille](https://www.raywenderlich.com/605079-logging-in-swift-oslog)
- [CocoaLumberjack GitHub -sivusto](https://github.com/CocoaLumberjack/CocoaLumberjack)
