---
aliases:
- /fr/javascript/converting-a-string-to-lower-case/
date: 2024-01-20 17:38:39.408946-07:00
description: "Convertir une cha\xEEne en minuscules, c'est transformer tous les caract\xE8\
  res alphab\xE9tiques en leur \xE9quivalent minuscule. C'est utile pour uniformiser\
  \ les\u2026"
lastmod: 2024-02-18 23:09:09.241452
model: gpt-4-1106-preview
summary: "Convertir une cha\xEEne en minuscules, c'est transformer tous les caract\xE8\
  res alphab\xE9tiques en leur \xE9quivalent minuscule. C'est utile pour uniformiser\
  \ les\u2026"
title: "Conversion d'une cha\xEEne de caract\xE8res en minuscules"
---

{{< edit_this_page >}}

## Quoi et Pourquoi ?

Convertir une chaîne en minuscules, c'est transformer tous les caractères alphabétiques en leur équivalent minuscule. C'est utile pour uniformiser les données textuelles, par exemple, lors de comparaisons de chaînes où la casse ne doit pas influencer le résultat.

## Comment faire :

```Javascript
// Transformer une chaîne en minuscules
let phrase = "Bonjour LE Monde!";
let phraseEnMinuscules = phrase.toLowerCase();

console.log(phraseEnMinuscules); // Affiche: "bonjour le monde!"
```

Simple et direct. La fonction `toLowerCase()` fait tout le travail.

## Plongée Profonde

Historiquement, la manipulation de casse en JavaScript est utilisée depuis l'apparition du langage pour traiter les données textuelles. À noter, `toLowerCase()` convertit selon les règles de casse de l'Unicode, ce qui signifie qu'elle peut gérer bien plus que les simples caractères ASCII.

Comme alternative, vous pourriez rencontrer `toLocaleLowerCase()`, qui prend en compte les spécificités locales de l'utilisateur, utile pour certains langages où la conversion de casse n'est pas uniforme.

Au niveau de l'implémentation, `toLowerCase()` traverse la chaîne donnée et remplace chaque lettre par sa version minuscule, si elle en a une. Si le caractère est déjà en minuscule ou n'a pas de version minuscule, il reste inchangé.

## Voir Aussi

- MDN Web Docs sur `toLowerCase()`: [MDN toLowerCase](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
- Comparaison de chaînes en JavaScript: [MDN LocaleCompare](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String/localeCompare)
- Unicode et JavaScript: [Mathias Bynens on Unicode](https://mathiasbynens.be/notes/javascript-unicode)
