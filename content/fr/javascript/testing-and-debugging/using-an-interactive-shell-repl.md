---
title:                "Utilisation d'une console interactive (REPL)"
aliases:
- /fr/javascript/using-an-interactive-shell-repl/
date:                  2024-01-26T04:15:22.189353-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilisation d'une console interactive (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/javascript/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Les coquilles interactives, ou REPLs (Read-Eval-Print Loops, Boucles de Lecture-Évaluation-Affichage), vous permettent d'exécuter du code à la volée, de tester des fonctions, des algorithmes, ou de jouer avec des idées. Elles sont les blocs-notes du codage, rapides et peu soignés, sans installer un environnement de développement complet.

## Comment faire :
Node.js est livré avec un REPL accessible via le terminal. Ouvrez-le, et vous êtes prêt à démarrer. Voici un avant-goût :

```javascript
$ node
> let sum = (a, b) => a + b;
undefined
> sum(5, 10);
15
> .exit
```

Simple, n'est-ce pas ? Définissez des variables, des fonctions, ou exécutez des boucles. Lorsque vous avez terminé, `.exit` vous ramène au monde réel.

## Plongée en profondeur
Les REPL existent depuis les années 1960 – LISP a été le pionnier du concept. L'idée : fournir un retour immédiat au programmeur. Des alternatives ? À part le REPL de Node.js, il y a les consoles basées sur les navigateurs comme les outils de développement de Chrome, les bac à sable en ligne comme JSFiddle, ou les IDE complets comme VSCode avec des terrains de jeux interactifs.

Sous le capot, les flux de travail REPL typiques :
1. Lire l'entrée
2. Compiler et exécuter le code
3. Imprimer la sortie
4. Boucler

C'est un cycle simple mais efficace qui a énormément influencé la codification interactive.

## Voir aussi
- [Documentation REPL de Node.js](https://nodejs.org/api/repl.html)
- [Introduction aux modules JavaScript sur les REPLs par Mozilla](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Modules)
- [JSFiddle](https://jsfiddle.net/)
