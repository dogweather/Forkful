---
title:                "Envoi d'une requête HTTP"
date:                  2024-01-20T17:59:10.916264-07:00
model:                 gpt-4-1106-preview
simple_title:         "Envoi d'une requête HTTP"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/arduino/sending-an-http-request.md"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Envoyer une requête HTTP, c'est demander des données à un serveur web. On le fait pour interagir avec le web : récupérer de l'info, envoyer des commandes, etc.

## How to: (Comment faire :)

```Arduino
#include <ESP8266WiFi.h>
#include <ESP8266HTTPClient.h>

const char* ssid = "YOUR_SSID"; // Remplacez avec votre SSID
const char* password = "YOUR_PASSWORD"; // Remplacez avec votre mot de passe

void setup() {
  Serial.begin(115200);
  WiFi.begin(ssid, password);
  
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connexion WiFi...");
  }
  
  Serial.println("Connecté au WiFi");
  
  if(WiFi.status() == WL_CONNECTED){
    HTTPClient http;
    http.begin("http://yourserver.com/api"); // URL de votre serveur
    
    int httpCode = http.GET(); // Lancer la requête HTTP GET
    
    if(httpCode > 0){
      String payload = http.getString(); // Réponse du serveur
      Serial.println(httpCode);
      Serial.println(payload);
    } else {
      Serial.println("Erreur lors de la connexion");
    }
    
    http.end(); // Fermer la connexion
  }
}

void loop() {
  // Rien ici
}
```

Sortie d'exemple :
```
Connexion WiFi...
Connecté au WiFi
200
{"data": "valeur"} // Ceci est un exemple de réponse en format JSON.
```

## Deep Dive (Plongée Profonde)
L'envoi de requêtes HTTP remonte aux débuts du web. C'était et ça reste la base de la communication web. Sur Arduino, utiliser un module comme l'ESP8266 est courant pour ajouter des capacités WiFi. Le code utilise la bibliothèque ESP8266HTTPClient qui simplifie le processus. Alternativement, le WiFi101 ou le Ethernet Shield peuvent servir pour des cartes non-WiFi natives. Pour l'implémentation, il faut gérer la connexion réseau, composer la requête et traiter la réponse. Chaque partie est critique.

## See Also (Voir Aussi)
- [ESP8266WiFi Library](https://arduino-esp8266.readthedocs.io/en/latest/esp8266wifi/readme.html) pour les détails sur la connexion WiFi avec l'ESP8266.
