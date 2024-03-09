---
title:                "Lire les arguments de la ligne de commande"
date:                  2024-03-08T21:55:38.848348-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Lire les arguments de la ligne de commande en Dart permet aux programmeurs d'entrer des données directement dans la console lors de l'exécution d'un programme Dart, améliorant son interactivité et sa flexibilité pour divers cas d'utilisation, y compris les scripts d'automatisation, les outils CLI ou le traitement par lots. Cette fonctionnalité est essentielle pour créer des applications en ligne de commande adaptables et conviviales.

## Comment faire :

Dart propose une approche simple pour accéder aux arguments de la ligne de commande via le `List<String> args` dans la méthode principale. Voici un exemple simple qui montre comment lire et utiliser les arguments de la ligne de commande.

```dart
// main.dart
void main(List<String> args) {
  print('Arguments de la ligne de commande :');
  for (var i = 0; i < args.length; i++) {
    print('${i + 1} : ${args[i]}');
  }
}
```

Pour exécuter ce programme Dart et passer des arguments de ligne de commande, utilisez le CLI Dart comme ceci :

```shell
dart run main.dart Bonjour le monde !
```

Sortie attendue :

```
Arguments de la ligne de commande :
1 : Bonjour
2 : le monde !
```

### Utilisation d'une bibliothèque tierce populaire : `args`

Bien que les capacités intégrées de Dart pour gérer les arguments de la ligne de commande soient robustes pour de nombreuses applications, le package `args` offre un moyen raffiné de définir et d'analyser les arguments de la ligne de commande pour des besoins plus complexes.

Tout d'abord, ajoutez le package `args` à votre `pubspec.yaml` :

```yaml
dependencies:
  args: ^2.0.0
```

Ensuite, utilisez-le dans votre programme comme suit :

```dart
// Utiliser le package 'args'
import 'package:args/args.dart';

void main(List<String> arguments) {
  final parser = ArgParser()..addOption('nom', abbr: 'n');
  final argResults = parser.parse(arguments);

  if (argResults.wasParsed('nom')) {
    print('Bonjour, ${argResults['nom']} !');
  } else {
    print('Aucun nom fourni.');
  }
}
```

Exécutez le programme avec un argument nommé :

```shell
dart run main.dart --nom=John
```

Sortie attendue :

```
Bonjour, John !
```

Cette simple introduction à l'analyse des arguments de la ligne de commande, à la fois nativement et avec la bibliothèque `args`, montre comment Dart peut gérer les entrées utilisateur directement depuis la console, ouvrant une voie à la création d'applications CLI plus interactives et dynamiques.
