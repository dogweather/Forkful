---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:04.994202-07:00
description: "Mettre une cha\xEEne de caract\xE8res en capitales implique de convertir\
  \ le premier caract\xE8re de chaque mot de la cha\xEEne en majuscule s'il est en\
  \ minuscule,\u2026"
lastmod: '2024-03-13T22:44:58.141355-06:00'
model: gpt-4-0125-preview
summary: "Mettre une cha\xEEne de caract\xE8res en capitales implique de convertir\
  \ le premier caract\xE8re de chaque mot de la cha\xEEne en majuscule s'il est en\
  \ minuscule, tout en gardant les caract\xE8res restants inchang\xE9s."
title: "Mettre en majuscule une cha\xEEne"
weight: 2
---

## Comment faire :
En C++, vous pouvez mettre une chaîne de caractères en capitales en utilisant la bibliothèque standard sans avoir besoin de bibliothèques tierces. Cependant, pour des comportements de capitalisation plus complexes ou spécifiques, des bibliothèques comme Boost peuvent être très utiles. Ci-dessous, des exemples illustrant les deux approches.

### En utilisant la bibliothèque standard C++ :
```cpp
#include <iostream>
#include <cctype> // pour std::tolower et std::toupper
#include <string>

std::string capitalizeString(const std::string& input) {
    std::string result;
    bool capitalizeNext = true;

    for (char ch : input) {
        if (std::isspace(ch)) {
            capitalizeNext = true;
        } else if (capitalizeNext) {
            ch = std::toupper(ch);
            capitalizeNext = false;
        }
        result += ch;
    }

    return result;
}

int main() {
    std::string text = "hello world from c++";
    std::string capitalizedText = capitalizeString(text);
    std::cout << capitalizedText << std::endl; // Sortie : "Hello World From C++"
}
```

### En utilisant la bibliothèque Boost :
Pour une manipulation de chaînes plus avancée, incluant la capitalisation sensible à la locale, vous pourriez vouloir utiliser la bibliothèque Boost String Algo.

D'abord, assurez-vous d'avoir installé et configuré la bibliothèque Boost dans votre projet. Ensuite, vous pouvez inclure les en-têtes nécessaires et utiliser ses fonctionnalités comme indiqué ci-dessous.

```cpp
#include <boost/algorithm/string.hpp>
#include <iostream>
#include <string>

int main() {
    std::string text = "hello world from c++";
    std::string capitalizedText = text;

    // mettre en majuscule la première lettre de chaque mot
    boost::algorithm::to_lower(capitalizedText); // s'assurer que la chaîne est en minuscules
    capitalizedText[0] = std::toupper(capitalizedText[0]); // mettre en majuscule le premier caractère

    for (std::size_t i = 1; i < capitalizedText.length(); ++i) {
        if (isspace(capitalizedText[i - 1])) { // mettre en majuscule après un espace
            capitalizedText[i] = std::toupper(capitalizedText[i]);
        }
    }

    std::cout << capitalizedText << std::endl; // Sortie : "Hello World From C++"
}
```

Dans ce cas, Boost simplifie certaines des tâches de manipulation de chaînes mais nécessite encore une approche personnalisée pour une véritable capitalisation, car elle offre principalement des utilitaires de transformation et de conversion de casse.
