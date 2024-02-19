---
aliases:
- /fr/lua/refactoring/
date: 2024-01-26 01:45:47.099488-07:00
description: "Le remaniement (ou refactoring) est l'art de retoucher le code existant\
  \ pour am\xE9liorer sa structure, sa lisibilit\xE9 et son efficacit\xE9 sans en\
  \ alt\xE9rer le\u2026"
lastmod: 2024-02-18 23:09:08.978787
model: gpt-4-0125-preview
summary: "Le remaniement (ou refactoring) est l'art de retoucher le code existant\
  \ pour am\xE9liorer sa structure, sa lisibilit\xE9 et son efficacit\xE9 sans en\
  \ alt\xE9rer le\u2026"
title: 'Refactoring : Mode d''emploi'
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Le remaniement (ou refactoring) est l'art de retoucher le code existant pour améliorer sa structure, sa lisibilité et son efficacité sans en altérer le comportement externe. Les programmeurs le font pour rendre leur code plus maintenable, réduire la complexité, et souvent comme une étape préliminaire avant d'ajouter de nouvelles fonctionnalités ou de corriger des bugs.

## Comment faire :
Prenons une simple fonction Lua et refactorisons-la. Nous commençons avec une fonction qui calcule la somme des nombres dans une liste mais est écrite sans beaucoup de souci pour l'efficacité ou la clarté :

```Lua
function sumList(numbers)
    local result = 0
    for i=1, #numbers do
        for j=1, #numbers do
            if i == j then
                result = result + numbers[i]
            end
        end
    end
    return result
end

print(sumList({1, 2, 3, 4})) -- Affiche : 10
```

Refactoriser pour une version plus efficace et lisible :
```Lua
function sumListRefactored(numbers)
    local result = 0
    for _, value in ipairs(numbers) do
        result = result + value
    end
    return result
end

print(sumListRefactored({1, 2, 3, 4})) -- Affiche toujours : 10
```

La version refactorisée supprime la boucle intérieure redondante, en utilisant `ipairs` pour parcourir la liste de manière propre.

## Plongée profonde
Historiquement, le refactoring provient de la communauté de programmation Smalltalk à la fin des années 80 et a été popularisé par le livre de Martin Fowler 'Refactoring: Improving the Design of Existing Code'. En Lua, refactoriser implique souvent de simplifier les conditionnelles complexes, de décomposer les grandes fonctions en fonctions plus petites, et d'optimiser l'utilisation des tables pour améliorer la performance.

Refactoriser en Lua a ses mises en garde ; la nature dynamique de Lua et le typage flexible peuvent rendre certains refactorings, comme renommer des variables ou changer les signatures de fonction, plus risqués si ce n'est pas fait avec prudence. Les outils d'analyse de code statique (comme `luacheck`) peuvent atténuer ces risques. Les alternatives incluent le développement piloté par les tests (TDD), où le code est continuellement refactorisé comme une partie intégrante du processus de développement, contrairement à une phase de refactoring séparée.

## Voir aussi
- "Programming in Lua" par Roberto Ierusalimschy pour les meilleures pratiques et exemples.
- "Refactoring: Improving the Design of Existing Code" par Martin Fowler pour les principes applicables à travers les langages.
- Annuaire LuaRocks (https://luarocks.org/) pour les outils et modules visant à maintenir et refactoriser le code Lua.
