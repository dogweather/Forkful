---
aliases:
- /fi/cpp/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:38.781906-07:00
description: "YAML, joka tarkoittaa \"YAML Ain't Markup Language\", on ihmisen luettavissa\
  \ oleva tiedon sarjallistamisformaatti. Ohjelmoijat k\xE4ytt\xE4v\xE4t sit\xE4\u2026"
lastmod: 2024-02-18 23:09:07.966253
model: gpt-4-0125-preview
summary: "YAML, joka tarkoittaa \"YAML Ain't Markup Language\", on ihmisen luettavissa\
  \ oleva tiedon sarjallistamisformaatti. Ohjelmoijat k\xE4ytt\xE4v\xE4t sit\xE4\u2026"
title: "Ty\xF6skentely YAML:n kanssa"
---

{{< edit_this_page >}}

## Mikä ja miksi?

YAML, joka tarkoittaa "YAML Ain't Markup Language", on ihmisen luettavissa oleva tiedon sarjallistamisformaatti. Ohjelmoijat käyttävät sitä asetustiedostoihin, datan dumpaamiseen ja hierarkkisen datan tallentamiseen sen luettavuuden ja helposti ymmärrettävän syntaksin ansiosta verrattuna XML:ään tai JSON:iin.

## Miten:

YAML:n käsittelyyn C++:ssa suosittu valinta on `yaml-cpp` kirjasto. Varmista ensin, että sinulla on `yaml-cpp` asennettuna ja oikein linkitettynä C++ projektiisi.

**YAML-tiedoston lukeminen:**

```cpp
#include <iostream>
#include <fstream>
#include <yaml-cpp/yaml.h>

int main() {
    YAML::Node config = YAML::LoadFile("config.yaml");
    
    if(config["title"]) {
        std::cout << "Otsikko: " << config["title"].as<std::string>() << std::endl;
    }
    
    return 0;
}
```

Olettaen, että `config.yaml` näyttää tältä:

```yaml
title: "Esimerkki YAML"
```

Yllä olevan C++ koodin suorittaminen tuottaisi:

```
Otsikko: Esimerkki YAML
```

**Kirjoittaminen YAML-tiedostoon:**

```cpp
#include <fstream>
#include <yaml-cpp/yaml.h>

int main() {
    YAML::Emitter out;
    out << YAML::BeginMap;
    out << YAML::Key << "title" << YAML::Value << "Esimerkki YAML";
    out << YAML::EndMap;
    
    std::ofstream fout("output.yaml");
    fout << out.c_str();
    
    return 0;
}
```

Tämä koodi luo `output.yaml` tiedoston sisällöllä:

```yaml
title: Esimerkki YAML
```

Nämä esimerkit toimivat perustietoina YAML-tiedostojen lukemisesta ja kirjoittamisesta C++:ssa käyttäen `yaml-cpp` kirjastoa. Tutki `yaml-cpp` dokumentaatiota monimutkaisempia rakenteita ja käyttötarkoituksia varten, kuten sekvenssejä, tageja ja edistyneempiä sarjallistamis- ja deserialisointitekniikoita varten.
