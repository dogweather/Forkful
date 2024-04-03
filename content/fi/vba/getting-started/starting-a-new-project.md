---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:03:19.327658-07:00
description: "Uuden projektin aloittaminen Visual Basic for Applications (VBA) -ohjelmassa\
  \ sis\xE4lt\xE4\xE4 ymp\xE4rist\xF6n pystytt\xE4misen is\xE4nt\xE4sovelluksen, kuten\
  \ Excelin, sis\xE4ll\xE4\u2026"
lastmod: '2024-03-13T22:44:56.401323-06:00'
model: gpt-4-0125-preview
summary: "Uuden projektin aloittaminen Visual Basic for Applications (VBA) -ohjelmassa\
  \ sis\xE4lt\xE4\xE4 ymp\xE4rist\xF6n pystytt\xE4misen is\xE4nt\xE4sovelluksen, kuten\
  \ Excelin, sis\xE4ll\xE4 teht\xE4vien automatisoimiseksi tai toiminnallisuuden laajentamiseksi."
title: Uuden projektin aloittaminen
weight: 1
---

## Miten:
Kun olet valmis aloittamaan uuden VBA-projektin, lähtökohtana on yleensä VBA-editorin käynnistäminen ja projektirunkosi alustaminen. Käydään läpi vaiheet käyttäen Exceliä isäntäsovelluksena:

1. **Avaa VBA-editori**: Excelissä paina `Alt + F11` päästäksesi VBA-editoriin.
2. **Lisää uusi moduuli**: Siirry valikkoon `Lisää > Moduuli` lisätäksesi uuden moduulin projektiisi. Tässä sijaitsee koodisi.
3. **Kirjoita ensimmäinen makrosi**: Koodataan yksinkertainen makro, joka näyttää viestilaatikon. Kirjoita seuraava koodi moduuliin:

```vb
Sub SayHello()
    MsgBox "Hello, World!", vbInformation, "Terveiset"
End Sub
```

4. **Suorita makrosi**: Paina `F5`, kun kursorisi on `SayHello`-aliohjelman sisällä, tai siirry kohtaan `Suorita > Suorita aliohjelma/käyttöliittymälomake` ja valitse `SayHello`. Sinun pitäisi nähdä viestilaatikko, jossa on "Hello, World!" ja "OK"-painike.

Esimerkkituloste:

```plaintext
Viestilaatikko, jossa lukee "Hello, World!".
```

5. **Tallenna projektisi**: Ennen poistumista varmista, että tallennat työsi. Jos Excel-työkirjaasi ei ollut aiemmin tallennettu, sinua pyydetään tallentamaan makroja sallivaan työkirjaan (`.xlsm`-tiedostomuoto).

## Syväsukellus
Visual Basic for Applications on ollut kulmakivi Microsoftin automaatiostrategioissa sen esittelyn jälkeen vuonna 1993. Sen edeltäjän, MacroBasicin, evolutiona syntyneenä VBA tarjosi robustimman ratkaisun parannetulla integraatiolla Microsoftin Officen sarjaan. Siirtyminen VBA:han oli merkittävä, merkiten siirtymän kohti monimutkaisempia skriptausmahdollisuuksia, jotka hyödynsivät oikeiden ohjelmointikielten tehoa.

Ikästään huolimatta VBA on yhä merkittävä modernissa toimistoympäristössä, suurelta osin sen syvän integraation ansiosta Officen tuotteissa ja monien organisaatioiden laajan perintökoodikannan vuoksi. On kuitenkin tärkeää huomata, että uudemmille, web-pohjaisille sovelluksille tai tehtäville, jotka vaativat enemmän skaalautuvuutta ja integraatiota Officen ulkopuolisten sovellusten kanssa, kielet ja kehykset kuten Python, sen rikkaan kirjastojen ekosysteemin kanssa, tai JavaScript Office-skripteille, tarjoavat modernimman ja monipuolisemman lähestymistavan. Nämä vaihtoehdot, vaikka vaativatkin jyrkemmän oppimiskurvin ja asetukset, tarjoavat laajemman soveltuvuuden ja tuen nykyaikaisille kehityskäytännöille, kuten versionhallinnalle ja julkaisuputkille.
