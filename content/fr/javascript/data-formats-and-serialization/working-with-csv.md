---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:20:14.674985-07:00
description: "Travailler avec les CSV (Valeurs S\xE9par\xE9es par des Virgules) en\
  \ JavaScript implique l'analyse ou la g\xE9n\xE9ration de fichiers CSV pour ing\xE9\
  rer des donn\xE9es\u2026"
lastmod: '2024-03-13T22:44:58.301529-06:00'
model: gpt-4-0125-preview
summary: "Travailler avec les CSV (Valeurs S\xE9par\xE9es par des Virgules) en JavaScript\
  \ implique l'analyse ou la g\xE9n\xE9ration de fichiers CSV pour ing\xE9rer des\
  \ donn\xE9es tabulaires provenant de sources externes ou exporter des donn\xE9es\
  \ pour une utilisation dans d'autres programmes."
title: Travailler avec CSV
weight: 37
---

## Comment faire :
JavaScript ne dispose pas de fonction intégrée pour l'analyse ou la génération de CSV comme c'est le cas avec JSON. Cependant, vous pouvez facilement gérer les données CSV en utilisant soit le JavaScript brut pour des tâches plus simples, soit en exploitant des bibliothèques puissantes comme `PapaParse` pour des scénarios plus complexes.

### Analyse Basique avec JavaScript Brut
Pour analyser une simple chaîne CSV en un tableau d'objets :

```javascript
const csv = `name,age,city
John,23,New York
Jane,28,Los Angeles`;

function parseCSV(csv) {
  const lines = csv.split("\n");
  const result = [];
  const headers = lines[0].split(",");

  for (let i = 1; i < lines.length; i++) {
    const obj = {};
    const currentline = lines[i].split(",");
    
    for (let j = 0; j < headers.length; j++) {
      obj[headers[j]] = currentline[j];
    }
    result.push(obj);
  }
  
  return result;
}

console.log(parseCSV(csv));
```
Sortie :

```
[
  { name: 'John', age: '23', city: 'New York' },
  { name: 'Jane', age: '28', city: 'Los Angeles' }
]
```

### Génération Basique vers CSV avec JavaScript Brut
Pour convertir un tableau d'objets en une chaîne CSV :

```javascript
const data = [
  { name: 'John', age: 23, city: 'New York' },
  { name: 'Jane', age: 28, city: 'Los Angeles' }
];

function arrayToCSV(arr) {
  const csv = arr.map(row => 
    Object.values(row).join(',')
  ).join('\n');
  
  return csv;
}

console.log(arrayToCSV(data));
```

Sortie :

```
John,23,New York
Jane,28,Los Angeles
```

### Utilisation de PapaParse pour des Tâches CSV Complexes
Pour des scénarios plus complexes, `PapaParse` est une bibliothèque robuste adaptée pour l'analyse et la génération de fichiers CSV avec des options pour les flux, les workers et la gestion de gros fichiers.

Analyser un fichier CSV ou une chaîne avec PapaParse :

```javascript
// Après avoir ajouté PapaParse à votre projet
const Papa = require('papaparse');
const csv = `name,age,city
John,23,New York
Jane,28,Los Angeles`;

Papa.parse(csv, {
  complete: function(results) {
    console.log("Analysé :", results.data);
  }
});
```

Produit :

```
Analysé : [
  ["name", "age", "city"],
  ["John", "23", "New York"],
  ["Jane", "28", "Los Angeles"]
]
```

Transformer un tableau en chaîne CSV avec PapaParse :

```javascript
const data = [
  { name: 'John', age: 23, city: 'New York' },
  { name: 'Jane', age: 28, city: 'Los Angeles' }
];

console.log(Papa.unparse(data));
```

Génère :

```
name,age,city
John,23,New York
Jane,28,Los Angeles
```

Ces exemples illustrent la gestion de CSV basique et avancée en JavaScript, permettant un échange de données facile dans les applications web et au-delà.
