---
title:                "Nykyisen päivämäärän hankkiminen"
aliases:
- /fi/vba/getting-the-current-date/
date:                  2024-02-01T21:55:02.513900-07:00
model:                 gpt-4-0125-preview
simple_title:         "Nykyisen päivämäärän hankkiminen"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/vba/getting-the-current-date.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mitä & Miksi?

Visual Basic for Applications (VBA) -ohjelmoinnissa nykyisen päivämäärän noutaminen on yleinen tehtävä, joka mahdollistaa ohjelmoijien dynaamisen työskentelyn päivämäärien kanssa makroissaan tai sovelluksissaan. Tämä toiminnallisuus on ratkaisevan tärkeää toimintoja kuten lokitus, tapahtumien aikaleimojen lisääminen tai päivämääräpohjaisten laskelmien tekeminen varten.

## Miten:

Nykyisen päivämäärän noutaminen VBA:ssa on suoraviivaista käyttämällä `Date`-funktiota, kun taas `Now`-funktio tarjoaa sekä nykyisen päivämäärän että ajan. Tässä on, miten voit työskennellä molempien kanssa:

```vb
Sub GetCurrentDate()
    ' Käyttäen Date-funktiota nykyisen päivämäärän saamiseksi
    Dim currentDate As Date
    currentDate = Date
    Debug.Print "Nykyinen päivämäärä: "; currentDate
    
    ' Käyttäen Now-funktiota nykyisen päivämäärän ja ajan saamiseksi
    Dim currentDateTime As Date
    currentDateTime = Now
    Debug.Print "Nykyinen päivämäärä ja aika: "; currentDateTime
End Sub
```

Kun ajat tämän makron, `Debug.Print`-metodi tulostaa nykyisen päivämäärän ja nykyisen päivämäärän ja ajan VBA-editorin Välitön-ikkunaan. Esimerkiksi:

```
Nykyinen päivämäärä: 12.4.2023
Nykyinen päivämäärä ja aika: 12.4.2023 15:45:22
```

Pidä mielessä, että päivämäärämuoto voi vaihdella käyttäjän tietokoneen järjestelmäasetusten mukaan.

## Syväsukellus

`Date`- ja `Now`-funktiot kapseloivat päivämäärän ja ajan käsittelyn kompleksisuuden Visual Basic for Applications -ohjelmoinnissa, tarjoten sovellustason abstraktion, joka tekee päivämäärien kanssa työskentelystä yksinkertaista ja intuitiivista. Historiallisesti päivämäärän ja ajan käsittely ohjelmoinnissa on ollut haastavaa, mukaan lukien eri aikavyöhykkeiden, kesäaikaan siirtymisen ja erilaisten päivämäärämuotojen käsittely.

VBA:ssa nämä funktiot tukeutuvat käyttöjärjestelmän alla olevaan päivämäärään ja aikaan, mikä tarkoittaa, että ne ovat käyttäjän lokaation ja järjestelmäasetusten vaikutuksen alaisena. Se on kaksiteräinen miekka, joka varmistaa yhdenmukaisuuden käyttäjän ympäristön kanssa, mutta myös edellyttää huolellista käsittelyä lokalisaation ja aikavyöhykkeen säätöissä globaaleissa sovelluksissa.

Vaikka VBA:n päivämäärä- ja aikafunktiot ovat täysin sopivia moniin sovelluksiin, erityisesti Officen automaation alueella, ne saattavat puuttua tarkkuutta tai yksityiskohtaisuutta vaativiin monimutkaisempiin sovelluksiin kuten korkeataajuiseen kaupankäyntiin tai tieteellisiin simulaatioihin. Tällaisissa tapauksissa muut ohjelmointiympäristöt tai kielet kuten Python tai C# saattavat tarjota monimutkaisempia päivämäärän ja ajan käsittelykirjastoja.

Kaikesta huolimatta valtaosalle tehtävistä, jotka liittyvät päivämääriin ja aikoihin Excelin, Wordin tai muiden Office-sovellusten kontekstissa, VBA:n `Date`- ja `Now`-funktiot tarjoavat tasapainon yksinkertaisuuden, suorituskyvyn ja käytön helppouden välillä, joka on vaikea voittaa.
