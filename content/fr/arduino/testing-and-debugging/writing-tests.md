---
title:                "Rédaction de tests"
date:                  2024-02-03T19:29:42.089248-07:00
model:                 gpt-4-0125-preview
simple_title:         "Rédaction de tests"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/arduino/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi et pourquoi ?

Écrire des tests dans l'environnement Arduino fait référence au processus de création de tests automatisés qui valident la fonctionnalité de votre code sur les appareils Arduino. Les programmeurs le font pour s'assurer que leur code fonctionne comme prévu, réduit les bugs et améliore la qualité de leurs projets, ce qui est particulièrement crucial dans les systèmes embarqués où le débogage peut être plus délicat.

## Comment faire :

Arduino ne dispose pas d'un cadre de test intégré comme certains autres environnements de programmation. Cependant, vous pouvez utiliser des bibliothèques tierces telles que `AUnit` pour le test unitaire du code Arduino. AUnit est inspiré de la bibliothèque intégrée d'Arduino, `ArduinoUnit`, et du cadre de test de Google, `Google Test`.

### Exemple avec AUnit :

Tout d'abord, installez AUnit via le gestionnaire de bibliothèques dans l'IDE Arduino : allez dans Sketch > Include Library > Manage Libraries... > recherchez AUnit et installez-le.

Ensuite, vous pouvez écrire des tests comme suit :

```cpp
#include <AUnit.h>

test(ledPinHigh) {
  const int ledPin = 13;
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, HIGH);
  assertTrue(digitalRead(ledPin));
}

test(ledPinLow) {
  const int ledPin = 13;
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, LOW);
  assertFalse(digitalRead(ledPin));
}

void setup() {
  Serial.begin(9600);
  aunit::TestRunner::run();
}

void loop() {
  // Vide
}
```
Après avoir téléchargé ce test sur votre carte Arduino, ouvrez le moniteur série pour voir les résultats du test. Vous devriez voir un résultat indiquant si chaque test a réussi ou échoué :

```
TestRunner démarré sur 2 test(s).
Test ledPinHigh réussi.
Test ledPinLow réussi.
Durée du TestRunner : 0,002 secondes.
Résumé du TestRunner : 2 réussis, 0 échoués, 0 ignorés, 0 expirés, sur 2 test(s).
```

Ce simple exemple démontre l'utilisation d'AUnit pour tester l'état d'une broche LED. En créant des tests, vous confirmez que votre Arduino se comporte comme prévu dans différentes conditions. Avec AUnit, vous pouvez écrire des tests plus complexes, des suites de tests, et profiter de fonctionnalités telles que les délais d'attente des tests et les procédures de configuration/démontage pour des scénarios plus avancés.
