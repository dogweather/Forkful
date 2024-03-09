---
title:                "Démarrer un nouveau projet"
date:                  2024-03-08T21:56:31.007523-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Commencer un nouveau projet en Dart implique de mettre en place un environnement propice au développement, aux tests et au déploiement efficaces. Les programmeurs initient de nouveaux projets Dart pour tirer parti de la performance optimale de Dart et de son écosystème robuste, en particulier pour le développement d'applications web et mobiles avec des frameworks comme Flutter.

## Comment faire :

1. **Installer Dart** :
   Assurez-vous que Dart est installé sur votre système. Sinon, vous pouvez le télécharger depuis [https://dart.dev/get-dart](https://dart.dev/get-dart). Vérifiez l'installation avec :

   ```shell
   dart --version
   ```

2. **Créer un Nouveau Projet Dart** :
   Utilisez le CLI de Dart pour générer un nouveau projet :

   ```shell
   dart create hello_dart
   ```

   Cette commande crée un nouveau répertoire `hello_dart` avec une simple application web ou console d'exemple, en fonction de votre sélection.

3. **Examiner la Structure du Projet** :

   Naviguez vers le répertoire de votre projet :

   ```shell
   cd hello_dart
   ```

   Un projet Dart typique comprend les fichiers et répertoires clés suivants :

   - `pubspec.yaml` : Fichier de configuration qui comprend les dépendances de votre projet et les contraintes SDK.
   - `lib/` : Répertoire où réside la majeure partie du code Dart.
   - `test/` : Répertoire pour les tests du projet.

4. **Ajouter des Dépendances** :
   Modifier `pubspec.yaml` pour ajouter des dépendances. Pour les projets web, envisagez d'ajouter `http`, un package populaire pour effectuer des requêtes HTTP :

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     http: ^0.13.3
   ```

   Après la modification, obtenez les dépendances :

   ```shell
   dart pub get
   ```

5. **Écrire Votre Premier Code Dart** :

   Dans le répertoire `lib/`, créez un nouveau fichier Dart, `main.dart`, et ajoutez un code Dart simple :

   ```dart
   // Importer la bibliothèque de base de Dart
   import 'dart:core';

   void main() {
     print('Hello, Dart!');
   }
   ```

6. **Exécuter Votre Application Dart** :

   Exécutez votre programme Dart avec :

   ```shell
   dart run
   ```

   La sortie doit être :

   ```
   Hello, Dart!
   ```

En suivant ces étapes, vous avez réussi à démarrer un nouveau projet Dart, de l'installation à l'exécution de votre premier morceau de code Dart. Cette connaissance de base prépare le terrain pour plonger plus profondément dans l'écosystème riche de Dart et ses capacités à construire des applications évolutives.
