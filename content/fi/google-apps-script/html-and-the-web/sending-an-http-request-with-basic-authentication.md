---
aliases:
- /fi/google-apps-script/sending-an-http-request-with-basic-authentication/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:02:28.045815-07:00
description: "HTTP-pyynn\xF6n l\xE4hett\xE4minen perusautentikaatiolla sis\xE4lt\xE4\
  \xE4 k\xE4ytt\xE4j\xE4nimen ja salasanan koodaamisen pyynn\xF6n otsikkoon suojattujen\
  \ resurssien k\xE4ytt\xF6\xF6n.\u2026"
lastmod: 2024-02-18 23:09:07.134827
model: gpt-4-0125-preview
summary: "HTTP-pyynn\xF6n l\xE4hett\xE4minen perusautentikaatiolla sis\xE4lt\xE4\xE4\
  \ k\xE4ytt\xE4j\xE4nimen ja salasanan koodaamisen pyynn\xF6n otsikkoon suojattujen\
  \ resurssien k\xE4ytt\xF6\xF6n.\u2026"
title: "HTTP-pyynn\xF6n l\xE4hett\xE4minen perusautentikoinnilla"
---

{{< edit_this_page >}}

## Mikä & Miksi?

HTTP-pyynnön lähettäminen perusautentikaatiolla sisältää käyttäjänimen ja salasanan koodaamisen pyynnön otsikkoon suojattujen resurssien käyttöön. Ohjelmoijat käyttävät tätä menetelmää palvelinpuolen autentikointiin, integroituakseen API-rajapintoihin, jotka vaativat perusautentikaatiota toimintojen, kuten datan noutamisen tai sisällön julkaisemisen, yhteydessä.

## Kuinka:

Google Apps Scriptillä HTTP-pyynnön lähettämiseksi perusautentikaatiolla käytät `UrlFetchApp`-palvelua yhdistettynä base64-koodattuun autentikointiotsikkoon. Tässä vaiheittainen opas:

1. **Koodaa Tunnistetiedot**: Ensin, koodaa käyttäjänimesi ja salasanasi base64-muotoon. Google Apps Script ei tarjoa natiivia base64-koodausfunktiota merkkijonoille, joten käytät tähän tarkoitukseen Utilities.base64Encode-funktiota.

```javascript
var username = 'YourUsername';
var password = 'YourPassword';
var encodedCredentials = Utilities.base64Encode(username + ':' + password);
```

2. **Aseta Pyynnön Valinnat**: Koodattujen tunnistetietojen valmistuttua, valmistele valintaobjekti HTTP-pyynnölle, sisältäen menetelmän ja otsikot.

```javascript
var options = {
  method: 'get', // tai 'post', 'put', tarpeidesi mukaan
  headers: {
    'Authorization': 'Basic ' + encodedCredentials
  }
  // tähän voidaan lisätä lisävalintoja kuten 'muteHttpExceptions' virheenkäsittelyä varten
};
```

3. **Tee Pyyntö**: Käytä `UrlFetchApp.fetch`-metodia kohde-URL:n ja valintaobjektin kanssa.

```javascript
var url = 'https://example.com/api/resource';
var response = UrlFetchApp.fetch(url, options);
Logger.log(response.getContentText());
```

Esimerkkituloste onnistuneesta pyynnöstä vaihtelee API:n vastauksen mukaan. JSON-pohjaisessa API:ssa saatat nähdä jotain tällaista:

```
{"status":"Success","data":"Tässä resurssin tiedot..."}
```

Varmista, että käsittelet mahdolliset HTTP-virheet tarkistamalla vastauskoodin tai käyttämällä `muteHttpExceptions`-valintaa hallitumpaan virheidenhallintaan.

## Syväsukellus

HTTP-pyynnön lähettäminen perusautentikaation kanssa on ollut standardi menetelmä monissa ohjelmointikielissä, kun tarvitaan pääsyä web-pohjaisiin resursseihin, joihin vaaditaan autentikointia. Google Apps Scriptin kontekstissa `UrlFetchApp` tarjoaa suoraviivaisen tavan suorittaa nämä HTTP-pyynnöt, mukaan lukien ne, jotka vaativat autentikointia. Perustunnistetietojen sisällyttäminen pyyntöjen otsikoihin on yksinkertainen, mutta tehokas menetelmä. Siinä on kuitenkin turvallisuuspuutteita, pääasiassa koska tunnistetiedot lähetetään tekstimuodossa, vain base64-koodattuna, mikä voidaan helposti purkaa, jos se keskeytetään.

Parempaa turvallisuutta varten suositellaan vaihtoehtoja, kuten OAuth 2.0, erityisesti, kun käsitellään arkaluonteisia tietoja tai toimintoja. Google Apps Script tukee OAuth 2.0:aa sisäänrakennetusti `OAuth2`-kirjaston avulla, mikä yksinkertaistaa autentikoinnin prosessia palveluita vastaan, jotka tukevat tätä protokollaa.

Perusautentikaatiosta huolimatta sen turvallisuuspuutteista johtuen sitä käytetään laajasti yksinkertaisissa tai sisäisissä sovelluksissa, jotka eivät ole alttiita laajemmalle internetille. Sen toteuttaminen on suoraviivaista, koska se vaatii vain yhden pyynnön asianmukaisesti asetettujen otsikoiden kanssa, mikä tekee siitä houkuttelevan vaihtoehdon nopeisiin integraatioihin tai APIeihin, joissa korkeamman turvallisuuden menetelmät eivät ole saatavilla. Ohjelmoijia kuitenkin kehotetaan harkitsemaan turvallisuusnäkökohtia ja tutkimaan turvallisempia vaihtoehtoja, kun sellaisia on saatavilla.
