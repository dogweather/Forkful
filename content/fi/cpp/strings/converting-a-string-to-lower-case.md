---
aliases:
- /fi/cpp/converting-a-string-to-lower-case/
date: 2024-01-20 17:37:55.368291-07:00
description: "Muuttaminen merkkijono pieniksi kirjaimiksi tarkoittaa kaikkien isojen\
  \ kirjainten muuntamista niiden pieniksi vastineiksi. Ohjelmoijat tekev\xE4t t\xE4\
  m\xE4n\u2026"
lastmod: 2024-02-18 23:09:07.929906
model: gpt-4-1106-preview
summary: "Muuttaminen merkkijono pieniksi kirjaimiksi tarkoittaa kaikkien isojen kirjainten\
  \ muuntamista niiden pieniksi vastineiksi. Ohjelmoijat tekev\xE4t t\xE4m\xE4n\u2026"
title: Merkkijonon muuntaminen pieniksi kirjaimiksi
---

{{< edit_this_page >}}

## What & Why? (Mikä ja Miksi?)
Muuttaminen merkkijono pieniksi kirjaimiksi tarkoittaa kaikkien isojen kirjainten muuntamista niiden pieniksi vastineiksi. Ohjelmoijat tekevät tämän yhdenmukaistaakseen dataa, helpottaakseen vertailua tai valmistellakseen tekstiä hakukoneille. 

## How to: (Kuinka tehdä:)
```C++
#include <iostream>
#include <string>
#include <algorithm>

int main() {
    std::string str = "Hei Maailma!";
    std::transform(str.begin(), str.end(), str.begin(), 
                   [](unsigned char c){ return std::tolower(c); });

    std::cout << str << std::endl; // tulostaa "hei maailma!"
    return 0;
}
```

## Deep Dive (Syväsukellus)
C++ ei ole tyypillisesti tarjonnut suoraviivaista tapaa muuttaa koko merkkijonoa pieneksi kirjaimiksi. Aiemmin ohjelmoijat tekivät sen itse kirjain kirjaimelta. C++11-standaardin tultua käyttöön `std::transform` ja `std::tolower` yhdistelmästä tuli suosittu tapa. Vaihtoehtoisesti voit kirjoittaa oman funktion tai käyttää kolmannen osapuolen kirjastoja, kuten Boost. C++20 toi `std::ranges`, joka tarjoaa elegantimman tavan iteroida läpi merkkijonoja. 

Ole tietoinen eri lokalisoinnin asetuksista käytettäessä `std::tolower`, koska se voi käyttäytyä eri tavoin eri alueellisten asetusten kanssa.

## See Also (Katso Myös)
- C++ Standard Library documentation: https://en.cppreference.com/w/
- Boost Algorithm Library: https://www.boost.org/doc/libs/release/libs/algorithm/
- C++20 `std::ranges`: https://en.cppreference.com/w/cpp/ranges

Tämä artikkeli antoi yleiskatsauksen merkkijonojen pienentämisestä C++:ssa. Rajattu, mutta hyödyllinen taito, joka parantaa tekstinkäsittelyä ohjelmissasi.
