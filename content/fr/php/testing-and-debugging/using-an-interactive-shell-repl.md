---
title:                "Utilisation d'une console interactive (REPL)"
aliases:
- fr/php/using-an-interactive-shell-repl.md
date:                  2024-01-26T04:16:27.182841-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilisation d'une console interactive (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/php/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Quoi et Pourquoi ?
Un shell interactif, ou REPL (Read-Eval-Print Loop, Boucle de Lire-Évaluer-Imprimer), vous permet d'écrire et d'exécuter du code PHP à la volée. C'est idéal pour l'expérimentation, le débogage, ou l'apprentissage, car vous pouvez tester des extraits de code sans le surcoût de créer un script complet.

## Comment faire :
Lancez le REPL PHP en exécutant `php -a` dans votre terminal. Voici un aperçu de son fonctionnement :

```php
php > echo "Bonjour, Monde !";
Bonjour, Monde !
php > $arr = [1, 2, 3];
php > print_r($arr);
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
)
```

Vous pouvez aussi définir des fonctions :

```php
php > function somme($a, $b) { return $a + $b; }
php > echo somme(5, 10);
15
```

## Plongée Profonde
Les REPL existent sous une forme ou une autre depuis les premiers jours de LISP dans les années 1960. Le shell interactif de PHP est moins avancé par rapport à ceux de langages comme Python ou JavaScript. Il ne conserve pas l'état entre les sessions et manque de fonctionnalités telles que l'auto-complétion. Pour un REPL PHP plus riche en fonctionnalités, envisagez des alternatives comme `psysh` ou `boris`. Ces shells tiers offrent de meilleurs outils d'introspection, la complétion par tabulation, et même un débogueur.

Sous le capot, le REPL de PHP fonctionne en compilant et exécutant chaque ligne de code au fur et à mesure de son entrée. Les limitations de cette approche deviennent évidentes avec des choses comme la redéclaration de classes, ce qui n'est pas possible dans la même session. C'est excellent pour des tests simples, mais cela peut devenir encombrant pour des tâches complexes.

## Voir Aussi
- [Manuel PHP - Shell interactif](https://www.php.net/manual/fr/features.commandline.interactive.php)
- [PsySH : Une console de développeur en temps réel, débogueur interactif et REPL pour PHP](https://psysh.org/)
- [Boris : Un petit REPL pour PHP](https://github.com/borisrepl/boris)
