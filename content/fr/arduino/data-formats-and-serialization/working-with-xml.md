---
date: 2024-01-26 04:27:30.551953-07:00
description: "Travailler avec le XML sur Arduino implique l'analyse et la manipulation\
  \ des donn\xE9es XML, g\xE9n\xE9ralement issues d'API web ou de fichiers de configuration.\u2026"
lastmod: '2024-03-13T22:44:58.140270-06:00'
model: gpt-4-0125-preview
summary: "Travailler avec le XML sur Arduino implique l'analyse et la manipulation\
  \ des donn\xE9es XML, g\xE9n\xE9ralement issues d'API web ou de fichiers de configuration."
title: Travailler avec XML
weight: 40
---

## Comment faire :
Nous utiliserons la bibliothèque `XMLWriter` pour créer du XML et la bibliothèque `tinyxml2` pour l'analyser. Installez d'abord les bibliothèques via le gestionnaire de bibliothèques dans votre IDE Arduino.

Création d'un document XML :

```Arduino
#include <XMLWriter.h>

void setup() {
  Serial.begin(9600);
  
  XMLWriter xml(&Serial); // Utilisation de Serial pour la sortie
  
  xml.header();
  xml.tag("greeting").tag("text").text("Bonjour, monde !").close().close();
  xml.flush();
}

void loop() {
}
```

Décodage d'une chaîne XML :

```Arduino
#include <tinyxml2.h>

tinyxml2::XMLDocument doc;
doc.Parse("<greeting><text>Bonjour, monde !</text></greeting>");

tinyxml2::XMLElement* text = doc.FirstChildElement("greeting")->FirstChildElement("text");
if (text != nullptr) {
  Serial.println(text->GetText());
}
```

Exemple de sortie :

```
<greeting>
  <text>Bonjour, monde !</text>
</greeting>
```

## Approfondissement
Le XML, ou Extensible Markup Language, est un langage de balisage qui définit un ensemble de règles pour coder des documents dans un format à la fois lisible par l'homme et par la machine. Il existe depuis la fin des années 90 et est utilisé de manière extensive dans divers domaines, surtout là où un échange de données indépendant de la plateforme est nécessaire. Les ressources mémoire limitées d'Arduino rendent le travail avec le XML plus difficile que sur un PC. Par conséquent, les bibliothèques légères sont cruciales. Bien que le JSON ait gagné en popularité pour l'échange de données en raison de sa syntaxe plus simple et de son empreinte plus petite, le XML est toujours largement utilisé, surtout lorsqu'il s'agit de systèmes ou d'applications héritées qui nécessitent une validation documentaire via des schémas. La clé de l'implémentation du XML sur Arduino est l'analyse en flux, qui lit le document par segments pour maintenir une faible utilisation de la mémoire.

## Voir aussi
- [Documentation de la bibliothèque TinyXML-2](https://leethomason.github.io/tinyxml2/)
- [Bibliothèque Arduino JSON](https://arduinojson.org/) pour une alternative lors du travail avec des données JSON.
- [Tutoriel XML de W3Schools](https://www.w3schools.com/xml/) pour un apprentissage général du XML.
- [Spécification XML du W3C](https://www.w3.org/XML/) pour les normes et recommandations officielles XML.
