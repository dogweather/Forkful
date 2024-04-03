---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:37.470979-07:00
description: "JSON, ou JavaScript Object Notation, est un format l\xE9ger d'\xE9change\
  \ de donn\xE9es, ce qui le rend parfait pour le stockage de donn\xE9es ou les fichiers\
  \ de\u2026"
lastmod: '2024-03-13T22:44:58.137908-06:00'
model: gpt-4-0125-preview
summary: "JSON, ou JavaScript Object Notation, est un format l\xE9ger d'\xE9change\
  \ de donn\xE9es, ce qui le rend parfait pour le stockage de donn\xE9es ou les fichiers\
  \ de configuration dans les projets Arduino."
title: Travailler avec JSON
weight: 38
---

## Comment faire :
Pour travailler avec le JSON dans Arduino, la bibliothèque `ArduinoJson` est un choix populaire en raison de sa facilité d'utilisation et de son efficacité. Elle permet d'analyser des chaînes JSON, de les modifier et de sérialiser des objets en retour en chaînes JSON. Voici comment l'utiliser :

1. **Installer la bibliothèque ArduinoJson** : Utilisez le Gestionnaire de bibliothèques dans l'IDE Arduino et installez "ArduinoJson".

2. **Désérialiser une chaîne JSON** : Voici comment analyser une chaîne JSON et extraire des valeurs.

```cpp
#include <ArduinoJson.h>

const char* json = "{\"sensor\":\"gps\",\"time\":1351824120,\"data\":[48.756080,2.302038]}";

void setup() {
  Serial.begin(9600);
  StaticJsonDocument<200> doc; // Ajustez la taille selon le document JSON
  DeserializationError error = deserializeJson(doc, json);

  if (error) {
    Serial.print(F("deserializeJson() a échoué : "));
    Serial.println(error.f_str());
    return;
  }

  const char* sensor = doc["sensor"]; // "gps"
  long time = doc["time"]; // 1351824120
  float latitude = doc["data"][0]; // 48.756080
  float longitude = doc["data"][1]; // 2.302038
  
  Serial.println(sensor);
  Serial.println(time);
  Serial.println(latitude, 6);
  Serial.println(longitude, 6);
}

void loop() {
  // Boucle vide
}
```

Exemple de sortie :

```
gps
1351824120
48.756080
2.302038
```

3. **Sérialiser en une chaîne JSON** : Voici comment créer une chaîne JSON à partir de données.

```cpp
#include <ArduinoJson.h>

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc; // Ajustez la taille selon les données
  doc["sensor"] = "gps";
  doc["time"] = 1351824120;
  JsonArray data = doc.createNestedArray("data");
  data.add(48.756080);
  data.add(2.302038);

  serializeJson(doc, Serial);
}

void loop() {
  // Boucle vide
}
```

Exemple de sortie (formaté pour une meilleure lisibilité) :

```
{"sensor":"gps","time":1351824120,"data":[48.756080,2.302038]}
```

L'utilisation efficace de la bibliothèque `ArduinoJson` permet aux projets Arduino de communiquer des structures de données complexes dans un format lisible par l'homme, facilitant le développement et l'intégration avec des services web.
