---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:57:34.631789-07:00
description: "Travailler avec JSON (JavaScript Object Notation) implique de parser\
  \ des donn\xE9es JSON \xE0 partir de cha\xEEnes de caract\xE8res vers des objets\
  \ Dart et vice\u2026"
lastmod: '2024-03-13T22:44:57.414523-06:00'
model: gpt-4-0125-preview
summary: "Travailler avec JSON (JavaScript Object Notation) implique de parser des\
  \ donn\xE9es JSON \xE0 partir de cha\xEEnes de caract\xE8res vers des objets Dart\
  \ et vice versa, une t\xE2che courante dans le d\xE9veloppement web et d'applications\
  \ pour l'\xE9change de donn\xE9es."
title: Travailler avec JSON
weight: 38
---

## Comment faire :
Dart offre un support intégré pour JSON avec la bibliothèque `dart:convert`, rendant le codage et le décodage de JSON simple. Voici des exemples illustrant les opérations de base :

**Parser une chaîne JSON en objet Dart :**
```dart
import 'dart:convert';

void main() {
  // Chaîne JSON d'exemple
  String jsonString = '{"name": "John", "age": 30, "email": "john@example.com"}';
  
  // Décodage JSON en Map Dart
  Map<String, dynamic> user = jsonDecode(jsonString);
  
  print('Bonjour, ${user['name']}! Vous avez ${user['age']} ans.');
  // Sortie : Bonjour, John! Vous avez 30 ans.
}
```

**Encoder un objet Dart en chaîne JSON :**
```dart
import 'dart:convert';

void main() {
  // Objet Dart d'exemple
  Map<String, dynamic> user = {
    'name': 'Jane',
    'age': 25,
    'email': 'jane@example.com'
  };
  
  // Encodage d'une Map Dart en JSON
  String jsonString = jsonEncode(user);
  
  print(jsonString);
  // Sortie : {"name":"Jane","age":25,"email":"jane@example.com"}
}
```

**Utiliser `json_serializable` pour des modèles complexes :**
Pour des modèles de données complexes, la sérialisation manuelle peut être fastidieuse. Le paquet `json_serializable` automatise ce processus. Il nécessite une configuration supplémentaire, y compris l'ajout de dépendances à votre fichier `pubspec.yaml` et la création de fichiers de build. Après la configuration, vous pouvez l'utiliser comme suit :

1. Définissez un modèle avec des annotations :
```dart
import 'package:json_annotation/json_annotation.dart';

part 'user.g.dart';

@JsonSerializable()
class User {
  String name;
  int age;
  String email;
  
  User({required this.name, required this.age, required this.email});
  
  factory User.fromJson(Map<String, dynamic> json) => _$UserFromJson(json);
  Map<String, dynamic> toJson() => _$UserToJson(this);
}
```

2. Générez le code de sérialisation :
Utilisez la commande du build runner pour générer le fichier `user.g.dart` :
```shell
flutter pub run build_runner build
```

3. Utilisez votre modèle :
```dart
void main() {
  // Parser JSON en User
  Map userMap = jsonDecode('{"name": "John", "age": 30, "email": "john@example.com"}');
  User user = User.fromJson(userMap);
  
  print('Utilisateur : ${user.name}, Âge : ${user.age}');
  // Sortie : Utilisateur : John, Âge : 30

  // Convertir User en JSON
  String jsonString = jsonEncode(user.toJson());
  print(jsonString);
  // Sortie : {"name":"John","age":30,"email":"john@example.com"}
}
```

Ces exemples illustrent les interactions de base et avancées avec JSON en Dart, permettant aux développeurs de gérer les tâches de sérialisation des données dans leurs applications de manière transparente.
