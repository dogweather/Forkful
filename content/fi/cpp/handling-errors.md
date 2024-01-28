---
title:                "Virheiden käsittely"
date:                  2024-01-26T00:50:13.044951-07:00
model:                 gpt-4-1106-preview
simple_title:         "Virheiden käsittely"
programming_language: "C++"
category:             "C++"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/cpp/handling-errors.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Virheiden käsittely tarkoittaa suunnitelmien tekemistä silloin, kun asiat menevät pieleen. Se on tärkeää, koska se auttaa välttämään kaatumisia ja tekee ohjelmistostasi vakaan ja käyttäjäystävällisen.

## Miten:
Tässä on perustason try-catch-lohko poikkeuksen käsittelyyn:

```cpp
#include <iostream>
#include <stdexcept>

int main() {
    try {
        heitä std::runtime_error("Hups! Jotain meni pieleen.");
    } poimi (const std::exception& e) {
        std::cerr << "Virhe: " << e.what() << std::endl;
    }
    return 0;
}
```

Esimerkkitulostus:
```
Virhe: Hups! Jotain meni pieleen.
```

## Syväsukellus
C++ on sisältänyt virheiden käsittelyn jo varhaisista päivistään lähtien. Perusmuoto oli paluuarvojen tarkistaminen. Jos olet kokenut tekijä, muistat standardin esiajat: C luokkineen ja manuaalinen virheiden tarkistus.

Sitten C++ toi poikkeukset tarjoten meille rakenteellisen tavan käsitellä odottamattomia ongelmia. Poikkeus heitetään käyttäen `heittää` ja poimitaan `try/catch`-lohkolla.

Kaksi virhetyyppiä tulee usein vastaan: loogiset virheet, kuten väärä laskelma, ja suoritusaikaiset virheet, kuten virheellisen muistiosoitteen käyttö. Poikkeukset ovat ihanteellisia suoritusaikaisille virheille. Loogisten virheiden osalta on usein parempi käyttää väitteitä eli assertioneja tai virhekoodeja.

Käynnissä on jatkuva keskustelu poikkeusten ja virhekoodien välillä. Poikkeukset voivat olla hitaampia ja saattaa johtaa monimutkaisiin ohjausvirtoihin. Virhekoodit, vaikkakin nopeampia, voivat tehdä koodista sekavaa ja vaikeammin ylläpidettävää. Se on kompromissi, joten käyttötapauksen tunteminen on avainasemassa.

C++17 toi `std::optional` ja `std::variant` mukanaan, jotka ovat vaihtoehtoja poikkeuksille. Ne ovat hyödyllisiä toimintoja varten, jotka saattavat palauttaa validin tuloksen tai eivät.

Poikkeusturva voi olla toinen päänsärky. Se koskee takeita, joita koodisi tarjoaa poikkeuksista huolimatta. On kolme tasoa: perus, vahva ja poikkeukseton. Mitä enemmän takeita, sitä monimutkaisempi koodisi voi olla.

Loppuajatuksia – virheiden käsittely on yhtä paljon taidetta kuin tiedettä. Se muovaa sitä, miten sovelluksesi selviää luonnossa. Älä käytä poikkeuksia liikaa. Tavoittele luettavaa, ylläpidettävää koodia.

## Katso Myös
- [cppreference poikkeustenkäsittelystä](https://en.cppreference.com/w/cpp/language/exceptions)
- [Bjarne Stroustrupin näkemys virheiden käsittelystä](http://www.stroustrup.com/except.pdf)
- [C++ Core Guidelines poikkeuksista](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#Re-exceptions)
