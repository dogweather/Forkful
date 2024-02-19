---
aliases:
- /fr/javascript/comparing-two-dates/
date: 2024-01-20 17:33:19.088451-07:00
description: "Comparer deux dates, c'est \xE9valuer leur ordre chronologique. On le\
  \ fait pour trier des \xE9v\xE8nements, programmer des rappels, ou calculer des\
  \ dur\xE9es."
lastmod: 2024-02-18 23:09:09.269941
model: gpt-4-1106-preview
summary: "Comparer deux dates, c'est \xE9valuer leur ordre chronologique. On le fait\
  \ pour trier des \xE9v\xE8nements, programmer des rappels, ou calculer des dur\xE9\
  es."
title: Comparer deux dates
---

{{< edit_this_page >}}

## What & Why?
Comparer deux dates, c'est évaluer leur ordre chronologique. On le fait pour trier des évènements, programmer des rappels, ou calculer des durées.

## How to:
```Javascript
// Créer deux objets Date
let date1 = new Date('2023-05-06');
let date2 = new Date('2023-05-07');

// Comparer les deux dates
if (date1 < date2) {
    console.log('date1 est avant date2');
} else if (date1 > date2) {
    console.log('date1 est après date2');
} else {
    console.log('date1 et date2 sont identiques');
}
```
Sortie possible :
```
date1 est avant date2
```

## Deep Dive
Comparer des dates est un principe de base en programmation, essentiel depuis l'introduction des premiers systèmes informatiques. Il existe des méthodes alternatives, comme comparer les timestamps avec `Date.now()` ou utiliser des bibliothèques externes comme Moment.js pour des comparaisons plus complexes.

En JavaScript, la comparaison directe fonctionne car les objets `Date` sont convertis en millisecondes depuis le 1er janvier 1970 (UTC) lorsque comparés. Les concepteurs de JavaScript ont inclut cette fonctionnalité dès le début, conscient de son importance pour les opérations basiques.

## See Also
- MDN Web Docs sur les objets Date : [Date - JavaScript | MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Date)
- Comparaison de dates avec Moment.js : [Moment.js | Docs](https://momentjs.com/docs/#/query/is-before/)
