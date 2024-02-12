---
title:                "Gestion des erreurs"
date:                  2024-01-26T00:50:03.931001-07:00
model:                 gpt-4-1106-preview
simple_title:         "Gestion des erreurs"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/cpp/handling-errors.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Gérer les erreurs implique de planifier pour les cas où les choses tournent mal. C'est essentiel car cela aide à éviter les plantages et rend votre logiciel robuste et convivial.

## Comment faire :
Voici un bloc try-catch de base pour gérer une exception :

```cpp
#include <iostream>
#include <stdexcept>

int main() {
    try {
        throw std::runtime_error("Oups ! Quelque chose a mal tourné.");
    } catch (const std::exception& e) {
        std::cerr << "Erreur : " << e.what() << std::endl;
    }
    return 0;
}
```

Exemple de sortie :
```
Erreur : Oups ! Quelque chose a mal tourné.
```

## Plongée en profondeur
C++ gère les erreurs depuis ses débuts. La forme la plus élémentaire était la vérification des valeurs de retour. Si vous avez de l'expérience, vous vous souvenez des jours pré-normes : C avec des classes et des vérifications d'erreur manuelles.

Puis sont arrivées les exceptions avec C++ pour nous offrir une manière structurée de faire face aux problèmes imprévus. Une exception est levée avec `throw` et capturée avec `try/catch`.

Deux types d'erreurs surviennent souvent : les erreurs logiques, comme un calcul erroné, et les erreurs d'exécution, comme l'accès à une adresse mémoire invalide. Les exceptions sont idéales pour les erreurs d'exécution. Pour les erreurs logiques, il est souvent préférable d'utiliser des assertions ou des codes d'erreur.

Il y a un débat en cours sur les exceptions par rapport aux codes d'erreur. Les exceptions peuvent être plus lentes et peuvent conduire à des flux de contrôle complexes. Les codes d'erreur, bien que plus rapides, peuvent rendre le code encombré et plus difficile à maintenir. C'est un compromis, donc connaître votre cas d'utilisation est la clé.

C++17 a introduit `std::optional` et `std::variant`, qui sont des alternatives aux exceptions. Ils sont utiles pour les fonctions qui peuvent ou non retourner un résultat valide.

La sécurité des exceptions peut être un autre casse-tête. Il s'agit des garanties que votre code fournit malgré les exceptions. Il existe trois niveaux : basique, fort et nothrow. Plus vous avez de garanties, plus votre code pourrait être complexe.

Pensées finales — la gestion des erreurs est autant un art qu'une science. Elle façonne la manière dont votre application survit dans la nature. N'abusez pas des exceptions. Visez un code lisible et maintenable.

## Voir également
- [cppreference sur la gestion des exceptions](https://en.cppreference.com/w/cpp/language/exceptions)
- [L'avis de Bjarne Stroustrup sur la gestion des erreurs](http://www.stroustrup.com/except.pdf)
- [Directives du C++ Core sur les exceptions](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#Re-exceptions)
