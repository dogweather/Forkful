---
title:                "HTTP-pyynnön lähettäminen perusautentikoinnilla"
date:                  2024-01-20T18:01:16.153281-07:00
model:                 gpt-4-1106-preview
simple_title:         "HTTP-pyynnön lähettäminen perusautentikoinnilla"
programming_language: "Bash"
category:             "Bash"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/bash/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why? (Mikä & Miksi?)
Lähetät HTTP-pyynnön perusautentikoinnilla liittääksesi käyttäjätunnuksen ja salasanan verkkoresurssin pyyntöön. Koodarit tekevät tämän päästäkseen käsiksi suojattuun sisältöön.

## How to: (Kuinka tehdä:)
```Bash
# Pyydä resurssia curl-komennolla ja Basic-autentikoinnilla
curl -u 'kayttajatunnus:salasana' http://esimerkki.com/salainen/sivu

# Koodin tuloste: serverin vastaus, esim. HTML-tiedot.
```

Voit myös koodata salasanan Base64-koodauksella:
```Bash
# Koodaa käyttäjätunnus ja salasana Base64-muotoon
base64_koodaus=$(echo -n 'kayttajatunnus:salasana' | base64)

# Lähetä pyyntö koodatulla merkkijonolla
curl -H "Authorization: Basic $base64_koodaus" http://esimerkki.com/salainen/sivu

# Koodin tuloste: serverin vastaus.
```

## Deep Dive (Sukellus syvemmälle)
Perusautentikointi on HTTP-protokollan varhainen menetelmä käyttäjän tunnistamiseen. Se sisältää käyttäjätunnuksen ja salasanan, jotka lähetetään Base64-koodattuna. Vuonna 2023 tämä ei ole turvallisin tapa, sillä HTTP ei suojaa tietoja. HTTPS:n käyttö on suositeltavaa, se salaa liikenteen. Vaihtoehtoina ovat esimerkiksi OAuth tai API-avaimet, jotka ovat turvallisempia tapoja autentikointiin.

Perusautentikointi on yksinkertainen implementoida; tarvitset vain käyttäjätunnuksen ja salasanan yhdistetyn merkkijonon, jonka sitten koodaat Base64-muotoon. Tyypillisesti käytetään `curl`-työkalua, mutta vastaavia toiminnallisuuksia tarjoavat myös muut HTTP-asiakasohjelmat, kuten `wget` tai ohjelmointikielten omat kirjastot.

## See Also (Katso myös)
- cURL viralliset dokumentit: [https://curl.haxx.se/docs/manpage.html](https://curl.haxx.se/docs/manpage.html)
- Base64-koodaus: [https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding)
