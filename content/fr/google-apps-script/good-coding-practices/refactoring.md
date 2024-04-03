---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:00:02.364171-07:00
description: "Le refactoring, dans le lexique de la programmation, d\xE9signe le processus\
  \ de restructuration du code informatique existant \u2013 modifier la facturation\
  \ sans\u2026"
lastmod: '2024-03-13T22:44:57.196013-06:00'
model: gpt-4-0125-preview
summary: "Le refactoring, dans le lexique de la programmation, d\xE9signe le processus\
  \ de restructuration du code informatique existant \u2013 modifier la facturation\
  \ sans changer son comportement externe \u2013 afin d'am\xE9liorer les attributs\
  \ non fonctionnels."
title: Refonte
weight: 19
---

## Comment procéder :
Dans Google Apps Script, un scénario courant qui bénéficie du refactoring est la simplification de scripts lourds qui interagissent avec Google Sheets ou Docs. Initialement, les scripts peuvent être écrits de manière rapide et sale pour obtenir des résultats rapidement. Avec le temps, à mesure que le script s’étoffe, il devient difficile à gérer. Prenons l'exemple d'un refactoring pour une meilleure lisibilité et efficacité.

**Script original :**

```javascript
function logSheetNames() {
  var sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  for (var i = 0; i < sheets.length; i++) {
    Logger.log(sheets[i].getName());
  }
}
```

Cette fonction enregistre le nom de chaque feuille dans un Google Spreadsheet. Bien qu’elle fonctionne correctement, elle utilise des pratiques JavaScript obsolètes et manque de clarté.

**Script refactoré :**

```javascript
function logSheetNames() {
  const sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  sheets.forEach(sheet => Logger.log(sheet.getName()));
}
```

Dans la version refactorée, nous sommes passés à l'utilisation de `const` pour les variables qui ne changent pas, rendant notre intention plus claire. Nous avons également utilisé la méthode `forEach`, une approche plus moderne et concise pour itérer sur les tableaux, augmentant la lisibilité.

**Exemple de sortie (pour les deux scripts) :**

La sortie dans Logger ressemblera à ceci, en supposant que votre document Google Sheets a deux feuilles nommées "Expenses" et "Revenue" :

```
[20-04-2023 10:00:00: INFO] Expenses
[20-04-2023 10:00:01: INFO] Revenue
```

Le script refactoré obtient le même résultat mais est plus propre et plus facile à comprendre en un coup d'œil.

## Analyse approfondie
Le refactoring dans Google Apps Script hérite en partie de ses principes de la pratique plus large du génie logiciel. Il est devenu plus reconnu et structuré en tant que concept à la fin des années 1990, notamment grâce au livre séminal de Martin Fowler "Refactoring: Improving the Design of Existing Code" (1999), qui a fourni un guide complet sur diverses techniques de refactoring. Bien que les spécificités du refactoring puissent varier d'un langage de programmation à l'autre en raison de leurs différences syntaxiques et fonctionnelles, l'objectif principal reste le même : améliorer le code sans altérer son comportement externe.

Dans le contexte de Google Apps Script, un aspect clé à considérer pendant le refactoring est les quotas de service et les limitations imposées par Google. Un code efficacement refactoré ne se lit pas seulement mieux, mais fonctionne également plus rapidement et de manière plus fiable dans ces contraintes. Par exemple, les opérations par lots (`Range.setValues()` au lieu de définir les valeurs une cellule à la fois) peuvent considérablement réduire le temps d'exécution et la consommation de quota.

Il est important de noter, cependant, que pour certains projets complexes, Google Apps Script pourrait être insuffisant en raison de ces mêmes limitations. Dans de tels cas, explorer des alternatives comme Google Cloud Functions ou le plus récent frère d'Apps Script, AppSheet, pourrait offrir une meilleure évolutivité et fonctionnalité.

En fin de compte, alors que le refactoring est une compétence essentielle dans la maintenance et l'amélioration des projets Google Apps Script, comprendre les limitations de l'environnement et envisager des solutions alternatives est tout aussi important pour fournir un code efficace, robuste et maintenable.
