---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:58:17.785204-07:00
description: "L'impression des sorties de d\xE9bogage implique de placer strat\xE9\
  giquement des d\xE9clarations de journalisation dans votre code pour afficher les\
  \ valeurs des\u2026"
lastmod: '2024-03-13T22:44:57.189024-06:00'
model: gpt-4-0125-preview
summary: "L'impression des sorties de d\xE9bogage implique de placer strat\xE9giquement\
  \ des d\xE9clarations de journalisation dans votre code pour afficher les valeurs\
  \ des variables, le flux d'ex\xE9cution ou les erreurs de messages pendant l'ex\xE9\
  cution."
title: "Affichage du d\xE9bogage"
weight: 33
---

## Comment faire :
Google Apps Script fournit la classe `Logger` pour le débogage de base, et pour des besoins plus avancés, la classe `console` introduite dans l'environnement d'exécution V8.

**Utiliser Logger :**

La classe Logger vous permet de consigner des messages de débogage, que vous pouvez consulter après l'exécution dans l'éditeur Apps Script sous `Affichage > Journaux`. Voici un exemple simple :

```javascript
function logSample() {
  var name = "Wired Reader";
  Logger.log("Bonjour, %s !", name);
}
```

Après avoir exécuté `logSample()`, vous pouvez consulter le journal avec "Bonjour, Wired Reader !" dans le visualiseur de journaux.

**Utiliser console.log avec l'environnement d'exécution V8 :**

Avec l'environnement d'exécution V8, `console.log` propose une syntaxe plus familière pour les développeurs venant d'autres langues :

```javascript
function consoleSample() {
  var status = 'actif';
  var count = 150;
  console.log(`Statut actuel : ${status}, Nombre : ${count}`);
}
```

Après l'exécution, accédez au journalisation Stackdriver dans `Affichage > Journalisation Stackdriver` pour voir la sortie. C'est plus puissant, supportant l'interpolation de chaînes et l'inspection d'objets, et s'intègre avec la journalisation de Google Cloud, offrant des journaux persistants et des capacités de filtrage avancées.

**Exemple de sortie de console.log :**

```
Statut actuel : actif, Nombre : 150
```

## Exploration en profondeur
Initialement, `Logger.log` était l'outil principal pour le débogage dans Google Apps Script, offrant une manière simple et directe d'imprimer la sortie pour inspection. Cependant, à mesure que les scripts devenaient plus complexes et intégrés aux services de Google Cloud Platform, le besoin d'une solution de journalisation plus robuste est devenu évident.

L'arrivée de l'environnement d'exécution V8 a apporté `console.log` dans le jeu. Cela non seulement aligne Google Apps Script avec la syntaxe JavaScript standard, rendant le langage plus accessible aux développeurs familiarisés avec JavaScript, mais exploite également l'infrastructure puissante des capacités de journalisation de Google Cloud. L'introduction de `console.log` et son intégration avec la Google Cloud Platform marquent une évolution significative des capacités de débogage au sein de Google Apps Script, fournissant aux développeurs une approche plus dynamique et évolutive pour surveiller et dépanner leurs scripts.

Alors que `Logger.log` suffit pour les besoins de débogage de base et les petits projets, `console.log` avec l'environnement d'exécution V8 offre une solution plus complète et à l'épreuve du futur. Cela inclut la capacité de conserver les journaux au-delà de la session d'exécution, de rechercher et de filtrer les journaux dans la console Google Cloud, et l'alignement global avec les pratiques modernes de développement JavaScript. Toutefois, les développeurs devraient évaluer leurs besoins par rapport à la complexité et à l'échelle de leurs projets lorsqu'ils choisissent entre ces options.
