---
title:                "Interpolation d'une chaîne de caractères"
date:                  2024-03-08T21:54:47.532900-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

L'interpolation de chaînes est le processus d'injecter directement des valeurs de variables dans des chaînes de caractères, souvent pour créer des messages significatifs sans concaténations fastidieuses. Les programmeurs le font pour un code plus propre, plus lisible et pour éviter les erreurs susceptibles de survenir dans des concaténations de chaînes complexes.

## Comment faire :

En Dart, l'interpolation de chaînes est simple, en utilisant le symbole `$` pour interpoler directement les expressions au sein des littéraux de chaîne :

```dart
void main() {
  String name = 'Dart';
  int year = 2023;
  // Interpolation simple de variable
  print('Apprendre $name en $year !');
  // Sortie : Apprendre Dart en 2023 !
  
  // Interpolation d'expressions
  print('Dans deux ans, ce sera ${year + 2}.');
  // Sortie : Dans deux ans, ce sera 2025.
}
```

Dans le cas où vous avez des expressions plus complexes ou souhaitez effectuer des opérations au sein même de la chaîne, encadrez l'expression par `${}`. Dart ne dispose pas de bibliothèques tierces populaires spécifiquement pour l'interpolation de chaînes car il est bien équipé nativement pour gérer des scénarios variés et complexes.
