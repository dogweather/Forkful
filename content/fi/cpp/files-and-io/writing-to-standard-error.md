---
title:                "Kirjoittaminen standardivirheeseen"
date:                  2024-02-03T19:32:40.336820-07:00
model:                 gpt-4-0125-preview
simple_title:         "Kirjoittaminen standardivirheeseen"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/cpp/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?

Virheilmoitusten kirjoittaminen standardivirheeseen (`stderr`) C++:ssa tarkoittaa virheviestien tai diagnostiikkatietojen tulostamista, jotka ovat erillään pääohjelman tulosteesta. Ohjelmoijat tekevät näin ohjatakseen virheet eri virtaan, mikä mahdollistaa helpomman vianjäljityksen ja virheenkäsittelyn erottamalla normaalin tulosteen virheviesteistä.

## Kuinka:

C++:ssa standardivirheeseen kirjoittaminen voidaan saavuttaa käyttämällä `cerr`-virtaa, joka on osa standardikirjastoa. Tässä on perusesimerkki:

```cpp
#include <iostream>

int main() {
    // Kirjoittaminen standarditulosteeseen
    std::cout << "Tämä on normaali viesti." << std::endl;
    
    // Kirjoittaminen standardivirheeseen
    std::cerr << "Tämä on virheviesti." << std::endl;
    
    return 0;
}
```

Esimerkkituloste:
```
Tämä on normaali viesti.
Tämä on virheviesti.
```

Tässä tapauksessa molemmat viestit ilmestyvät tyypillisesti terminaaliisi, mutta voit ohjata ne erikseen komentorivillä. Esimerkiksi, voit lähettää standarditulosteen tiedostoon samalla kun annat virheiden näkyä näytöllä.

Monimutkaisempaan lokitukseen ja virheenkäsittelyyn voidaan käyttää kolmannen osapuolen kirjastoja, kuten `spdlog` tai `boost.log`. Nämä kirjastot tarjoavat parannettuja ominaisuuksia lokitukseen, mukaan lukien muotoilu, lokitasot ja tiedostotulostus.

Tässä on esimerkki siitä, miten saatat käyttää `spdlog`ia kirjoittaaksesi virheviestin:

```cpp
#include "spdlog/spdlog.h"

int main() {
    // Alusta spdlog
    spdlog::info("Tämä on normaali viesti.");
    spdlog::error("Tämä on virheviesti.");
    
    return 0;
}
```

Huom: `spdlog`in käyttämiseksi sinun täytyy lisätä se projektiisi. Voit tehdä tämän kloonaamalla varaston GitHubista tai käyttämällä paketinhallintajärjestelmää kuten `vcpkg` tai `conan`. 

Muista, että valinta suorien standardivirtojen tai kirjaston kuten `spdlog` käytön välillä riippuu sovelluksesi monimutkaisuudesta ja erityistarpeistasi virheenkäsittelyn ja lokituksen suhteen.
