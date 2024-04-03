---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:59.300172-07:00
description: "Mettre en majuscule une cha\xEEne de caract\xE8res consiste \xE0 convertir\
  \ le premier caract\xE8re de chaque mot en majuscule, tout en s'assurant que les\
  \ autres\u2026"
lastmod: '2024-03-13T22:44:58.088468-06:00'
model: gpt-4-0125-preview
summary: "Mettre en majuscule une cha\xEEne de caract\xE8res consiste \xE0 convertir\
  \ le premier caract\xE8re de chaque mot en majuscule, tout en s'assurant que les\
  \ autres restent en minuscule."
title: "Mettre en majuscule une cha\xEEne"
weight: 2
---

## Comment faire :
Arduino, principalement connu pour son interaction avec le matériel, inclut également des capacités de manipulation de chaînes de caractères basiques via son objet `String`. Cependant, il n'a pas de fonctions `capitalize` directe comme on peut le voir dans les langages de plus haut niveau. Ainsi, nous implémentons la capitalisation en itérant sur une chaîne de caractères et en appliquant des transformations de casse.

Voici un exemple simple sans utiliser de bibliothèques tierces :

```cpp
String capitalizeString(String input) {
  if (input.length() == 0) {
    return ""; // Retourner une chaîne vide si l'entrée est vide
  }
  input.toLowerCase(); // Convertir d'abord la chaîne entière en minuscules
  input.setCharAt(0, input.charAt(0) - 32); // Mettre en majuscule le premier caractère
  
  // Mettre en majuscule les lettres qui suivent un espace
  for (int i = 1; i < input.length(); i++) {
    if (input.charAt(i - 1) == ' ') {
      input.setCharAt(i, input.charAt(i) - 32);
    }
  }
  return input;
}

void setup() {
  Serial.begin(9600);
  String testStr = "hello arduino world";
  String capitalizedStr = capitalizeString(testStr);
  Serial.println(capitalizedStr); // Sortie : "Hello Arduino World"
}

void loop() {
  // Boucle vide
}
```

Ce fragment de code définit une fonction `capitalizeString` qui convertit d'abord la chaîne entière en minuscules pour standardiser sa casse. Il met ensuite en majuscule le premier caractère et tout caractère qui suit un espace, mettant effectivement en majuscule chaque mot dans la chaîne d'entrée. Notez que cette mise en œuvre rudimentaire suppose un encodage de caractères ASCII et peut nécessiter des ajustements pour un support complet de l'Unicode.

Actuellement, il n'y a pas de bibliothèques tierces largement adoptées spécifiquement pour la manipulation de chaînes dans l'écosystème Arduino, principalement en raison de son accent sur l'interaction matérielle et l'efficacité. Cependant, l'exemple fourni est une manière directe d'atteindre la capitalisation de chaînes au sein de l'environnement de programmation Arduino.
