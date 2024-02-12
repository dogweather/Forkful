---
title:                "Verkkosivun lataaminen"
aliases:
- /fi/bash/downloading-a-web-page/
date:                  2024-01-20T17:43:14.143267-07:00
model:                 gpt-4-1106-preview
simple_title:         "Verkkosivun lataaminen"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/bash/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? / Mitä ja miksi?
Ladataan verkkosivun sisältö palvelimelta omalle koneelle. Ohjelmoijat tekevät tämän, kun tarvitaan tietoa automaattisesti tai testataan sovelluksia.

## How to: / Kuinka:
```Bash
# Lataa sivun sisältö wget-komennolla
wget https://example.com

# Tai käytä curl-komentoa ja tallenna tulos tiedostoon
curl https://example.com -o example_page.html

# Tarkista lataus
cat example_page.html
```
Lataus onnistui ja sivun HTML on nyt paikallisessa tiedostossa.

## Deep Dive / Syväsukellus:
Historiallisesti web-sivujen lataaminen liittyy tiedon hakemiseen ja webin indeksointiin (esim. hakukoneet). Eri työkalut, kuten `wget` ja `curl`, ovat yleisessä käytössä. `wget` on hyvä massalatausten aiheuttamaan kuormaan ja toimii rekursiivisesti. `curl` taas on monipuolinen yhden sivun tai API-vastauksen lataamiseen. Tärkeää on hallita työkalujen optiot ja käyttöoikeudet – liiallinen lataaminen voi aiheuttaa palvelunestohyökkäyksen.

## See Also / Katso myös:
- `man wget` ja `man curl` komentorivillä: lisätiedot ja käyttöohjeet.
- [GNU Wget Manual](https://www.gnu.org/software/wget/manual/wget.html): Tarkka dokumentaatio `wget`-komennolle.
- [curl Documentation](https://curl.se/docs/): Syvällistä tietoa `curl`-komennon käytöstä.
