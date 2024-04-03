---
date: 2024-01-26 03:42:22.120580-07:00
description: "Enlever les guillemets d'une cha\xEEne signifie retirer les caract\xE8\
  res de guillemets simples (`'`) ou doubles (`\"`) qui d\xE9finissent les litt\xE9\
  raux de cha\xEEne\u2026"
lastmod: '2024-03-13T22:44:57.423900-06:00'
model: gpt-4-0125-preview
summary: "Enlever les guillemets d'une cha\xEEne signifie retirer les caract\xE8res\
  \ de guillemets simples (`'`) ou doubles (`\"`) qui d\xE9finissent les litt\xE9\
  raux de cha\xEEne dans le code."
title: "Retirer les guillemets d'une cha\xEEne"
weight: 9
---

## Comment faire :
Voici votre guide direct pour libérer ces maudits marqueurs de citation de vos chaînes dans TypeScript.

```typescript
// Option A : Remplacer les guillemets simples ou doubles en utilisant regex
function removeQuotes(input: string): string {
  return input.replace(/^["']|["']$/g, '');
}

console.log(removeQuotes(`"Quoted string"`)); // Quoted string
console.log(removeQuotes(`'Another one'`)); // Another one

// Option B : Traitement des chaînes qui commencent et se terminent par des guillemets différents
function removeMismatchedQuotes(input: string): string {
  return input.replace(/^(['"])(.*?)(?<!\1)\1$/, '$2');
}

console.log(removeMismatchedQuotes(`"Mismatched'`)); // "Mismatched'

// Option C : Suppression de plusieurs types de guillemets
function removeAllQuotes(input: string): string {
  return input.replace(/['"]+/g, '');
}

console.log(removeAllQuotes(`"'Mix'n'Match'"`)); // Mix'n'Match
```

## Exploration en profondeur
Bien avant que TypeScript ne soit même une chose, les codeurs JavaScript étaient déjà confrontés aux shenanigans des guillemets, et l'histoire est à peu près la même pour TypeScript. À mesure que les temps changent, la manière dont nous découpons les chaînes évolue également. De nos jours, avec la force musculaire de regex, nous mettons de côté l'utilisation de découpage de chaîne maladroit ou d'autres méthodes fastidieuses.

Bien que les exemples ci-dessus devraient couvrir la plupart de vos besoins, rappelez-vous, le citation peut devenir complexe. Les guillemets nichés, appariés de manière incohérente et échappés sont les farceurs qui attendent de vous faire trébucher. Pour ceux-ci, vous pourriez avoir besoin de modèles plus sophistiqués ou même de parseurs pour gérer chaque cas tordu.

Des alternatives ? Certains préfèrent utiliser des bibliothèques comme lodash, avec des méthodes telles que `trim` et `trimStart` / `trimEnd`, qui peuvent être adaptées pour couper les guillemets si vous définissez les caractères que vous souhaitez tailler.

Et pour vous, les enthousiastes de TypeScript, n'oublions pas les types. Bien que nous traitons ici principalement avec des chaînes, lorsque vous travaillez avec une entrée utilisateur ou l'analyse, l'ajout de quelques garde-fous de type ou même de génériques peut aider à assurer que vous gardez votre code aussi sécurisé que vos guillemets sont taillés.

## Voir aussi
Consultez ces points chauds virtuels pour plus d'infos :

- MDN Web Docs sur regex (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
- Documentation officielle de TypeScript (https://www.typescriptlang.org/docs/)
- You Don't Need Lodash/Underscore – Aides pour les chaînes de caractères (https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore#strings)
- Stack Overflow : Parcourez les tranchées où d'innombrables développeurs ont lutté contre les catastrophes de guillemets (https://stackoverflow.com/)
