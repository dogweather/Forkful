---
title:                "Travailler avec YAML"
aliases:
- /fr/cpp/working-with-yaml/
date:                  2024-02-03T19:24:50.238706-07:00
model:                 gpt-4-0125-preview
simple_title:         "Travailler avec YAML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/cpp/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi et pourquoi ?

YAML, qui signifie "YAML Ain't Markup Language" (YAML n'est pas un langage de balisage), est un format de sérialisation de données lisible par l'humain. Les programmeurs l'utilisent pour les fichiers de configuration, le dumping de données et le stockage de données hiérarchiques en raison de sa lisibilité et de sa syntaxe facile à comprendre par rapport à XML ou JSON.

## Comment faire :

Pour travailler avec YAML en C++, un choix populaire est la bibliothèque `yaml-cpp`. Assurez-vous d'abord que vous avez installé `yaml-cpp` et qu'il est correctement lié à votre projet C++.

**Lire un fichier YAML :**

```cpp
#include <iostream>
#include <fstream>
#include <yaml-cpp/yaml.h>

int main() {
    YAML::Node config = YAML::LoadFile("config.yaml");
    
    if(config["title"]) {
        std::cout << "Titre : " << config["title"].as<std::string>() << std::endl;
    }
    
    return 0;
}
```

Étant donné un `config.yaml` qui ressemble à ceci :

```yaml
title: "Exemple YAML"
```

L'exécution du code C++ ci-dessus produirait :

```
Titre : Exemple YAML
```

**Écrire dans un fichier YAML :**

```cpp
#include <fstream>
#include <yaml-cpp/yaml.h>

int main() {
    YAML::Emitter out;
    out << YAML::BeginMap;
    out << YAML::Key << "title" << YAML::Value << "Exemple YAML";
    out << YAML::EndMap;
    
    std::ofstream fout("output.yaml");
    fout << out.c_str();
    
    return 0;
}
```

Ce code créera un `output.yaml` avec le contenu :

```yaml
title: Exemple YAML
```

Ces exemples servent d'introduction de base à la lecture et à l'écriture de fichiers YAML en C++ en utilisant la bibliothèque `yaml-cpp`. Pour des structures plus complexes et des cas d'utilisation, explorez la documentation de `yaml-cpp` pour des fonctionnalités telles que les séquences, les tags, et des techniques de sérialisation et désérialisation plus avancées.
