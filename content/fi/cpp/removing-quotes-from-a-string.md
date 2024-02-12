---
title:                "Merkkijonosta lainausmerkkien poistaminen"
aliases:
- fi/cpp/removing-quotes-from-a-string.md
date:                  2024-01-26T03:38:03.904983-07:00
model:                 gpt-4-0125-preview
simple_title:         "Merkkijonosta lainausmerkkien poistaminen"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/cpp/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Lainausmerkkien poistaminen merkkijonosta tarkoittaa ärsyttävien kaksin- tai yksinkertaisten merkkien (‘ tai ”) kuorimista tekstistämme. Ohjelmoijat tekevät tätä usein syötteen puhdistamiseksi, tekstin tallentamiseksi tietokantaan tai merkkijonojen esikäsittelyksi ilman lainausmerkkien sotkua.

## Kuinka:
Tässä suoraviivainen tapa heittää nuo lainausmerkit roskakoriin C++:ssa:

```cpp
#include <iostream>
#include <algorithm>

std::string remove_quotes(std::string input) {
    input.erase(std::remove(input.begin(), input.end(), '\"'), input.end());
    input.erase(std::remove(input.begin(), input.end(), '\''), input.end());
    return input;
}

int main() {
    std::string original = R"("Hei, 'Maailma'!")";
    std::string no_quotes = remove_quotes(original);
    std::cout << no_quotes << std::endl;
    return 0;
}
```

Aja tämä, ja saat:

```
Hei, Maailma!
```

Kas vain! Lainausmerkit ovat hävinneet.

## Syvempi sukellus
Lainausmerkit ovat olleet tekstiharmi tietojenkäsittelyn alusta lähtien. Aikanaan näit ohjelmoijien vaivalloisesti luuppavan jokaisen merkin läpi suodattaakseen nuo lainausmerkit pois. Nykyään meillä on Standard Template Libraryn (STL) `std::remove` tehdäksemme raskaan työn.

Vaihtoehtoja? Tietysti! Voisit käyttää säännöllisiä lausekkeita `std::regex` avulla kohdistaaksesi lainausmerkkeihin, mutta se on vähän kuin käyttäisi lekaa pähkinän murtamiseen - tehokasta, mutta voi olla liioittelua yksinkertaisille tehtäville. Ne, jotka suosivat uudempia C++-makuja, saattavat kokeilla `std::string_view'ta` muuttamattomiin lähestymistapoihin.

Toteutusmielessä, muista että `std::remove` ei itse asiassa poista elementtejä säiliöstä; se siirtää poistamattomat elementit eteenpäin ja palauttaa iterattorin uuden alueen loppuun. Siksi tarvitsemme `erase`-metodin leikkaamaan ei-toivotun hännän pois.

## Katso myös
- C++ `std::remove` viite: [cppreference.com](https://en.cppreference.com/w/cpp/algorithm/remove)
- Lisää `std::string` manipulaatiosta: [cplusplus.com](http://www.cplusplus.com/reference/string/string/)
