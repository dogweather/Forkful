---
aliases:
- /fi/php/sending-an-http-request-with-basic-authentication/
date: 2024-01-20 18:02:38.022706-07:00
description: "L\xE4hett\xE4m\xE4ll\xE4 HTTP-pyynn\xF6n perusautentikoinnilla, ohjelmoija\
  \ voi turvata p\xE4\xE4syn tiettyihin web-resursseihin. T\xE4t\xE4 k\xE4ytet\xE4\
  \xE4n yleisesti API:en suojattuun\u2026"
lastmod: 2024-02-18 23:09:07.711226
model: gpt-4-1106-preview
summary: "L\xE4hett\xE4m\xE4ll\xE4 HTTP-pyynn\xF6n perusautentikoinnilla, ohjelmoija\
  \ voi turvata p\xE4\xE4syn tiettyihin web-resursseihin. T\xE4t\xE4 k\xE4ytet\xE4\
  \xE4n yleisesti API:en suojattuun\u2026"
title: "HTTP-pyynn\xF6n l\xE4hett\xE4minen perusautentikoinnilla"
---

{{< edit_this_page >}}

## What & Why? - Mikä & Miksi?
Lähettämällä HTTP-pyynnön perusautentikoinnilla, ohjelmoija voi turvata pääsyn tiettyihin web-resursseihin. Tätä käytetään yleisesti API:en suojattuun yhteyteen, kun halutaan varmistaa että käyttäjällä on oikea käyttäjätunnus ja salasana.

## How to: - Kuinka tehdä:
PHP tarjoaa `curl`-toiminnon HTTP-pyyntöjen käsittelyyn perusautentikoinnin kanssa. Tässä nopea esimerkki:

```php
<?php
$curl = curl_init();

curl_setopt($curl, CURLOPT_URL, "https://example.com/api/data");
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);
curl_setopt($curl, CURLOPT_USERPWD, "kayttajatunnus:salasana");

$response = curl_exec($curl);
$status = curl_getinfo($curl, CURLINFO_HTTP_CODE);

curl_close($curl);

if ($status == 200) {
    echo "Yhteys onnistui:\n";
    print_r($response);
} else {
    echo "Virhe: HTTP-tilakoodi " . $status . "\n";
}
?>
```
Jos käyttäjätunnus ja salasana ovat oikein, saat vastauksena API:n palauttamat tiedot. Virheellisillä tunnuksilla saat HTTP-tilakoodin, joka ilmoittaa ongelmasta.

## Deep Dive - Syväsukellus:
Perusautentikointi on HTTP-protokollan varhainen turvaominaisuus. Se lähettää käyttäjätunnuksen ja salasanan Base64-koodattuna, joka ei ole turvallisin tapa ilman HTTPS-protokollaa. Nykyään OAuth 2.0 ja muut token-pohjaiset käsittelyt ovat yleisiä, mutta perusautentikointia käytetään edelleen yksinkertaisten autentikointitarpeiden hoitoon.

Perusautentikoinnin yksinkertaisuus on sen etu ja haitta. Se on helposti toteutettavissa, mutta ei kovin turvallinen avoimissa verkoissa. HTTPS:n kanssa käytettynä perusautentikointi on riittävä suoja monille sovelluksille.

PHP:ssä `curl` toimintojen lisäksi myös file_get_contents ja stream_context_create funktiot voivat lähettää perusautentikointia vaativia pyyntöjä. Oikea valinta riippuu tarpeestasi ja siitä, miten haluat käsitellä virheitä ja vastauksia.

## See Also - Katso Myös:
- PHP:n virallinen `curl` dokumentaatio: [php.net/manual/en/book.curl.php](https://www.php.net/manual/en/book.curl.php)
- PHP tietoturvasuositukset: [php.net/manual/en/security.php](https://www.php.net/manual/en/security.php)
- Tietoa HTTP-autentikointiprotokollista: [developer.mozilla.org/en-US/docs/Web/HTTP/Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication)
