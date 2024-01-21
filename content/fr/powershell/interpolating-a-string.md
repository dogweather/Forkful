---
title:                "Interpolation de chaînes de caractères"
date:                  2024-01-20T17:51:17.807415-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolation de chaînes de caractères"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/powershell/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Interpoler une chaîne, c'est insérer des valeurs de variables directement dedans. C'est utilisé pour composer des messages ou des commandes de façon fluide et dynamique, sans recoller des bouts de chaîne à la mano.

## How to:
En PowerShell, utilisez `"${ma_variable}"` pour interpoler. Voilà un exemple:

```PowerShell
$planete = 'Terre'
$message = "Salut, habitants de la ${planete}!"
Write-Host $message
```
Sortie: `Salut, habitants de la Terre!`

Plus complexe? Essayez ça:

```PowerShell
$utilisateur = 'Alex'
$nombreDeConnexions = 42
$message = "L'utilisateur ${utilisateur} s'est connecté ${nombreDeConnexions} fois."
Write-Host $message
```
Sortie: `L'utilisateur Alex s'est connecté 42 fois.`

## Deep Dive
Avant PowerShell, les gens utilisaient d'autres méthodes, comme la concaténation en C# avec `+`, ou encore des formats de chaînes. Dans PowerShell, `${nom_variable}` est la syntaxe d'interpolation introduite en version 3.0, simplifiant la composition des chaînes.

Il y a aussi `-f`, l'opérateur de mise en forme, plus verbeux mais toujours utile pour des situations complexes:

```PowerShell
$produit = 'livre'
$prix = 30
Write-Host ('Le {0} coûte {1:C}' -f $produit, $prix)
```
Sortie: `Le livre coûte 30,00 €`

N'oubliez pas, l'interpolation nécessite des doubles guillemets `"`. Avec des simples `'`, ça ne marche pas, les variables ne seront pas remplacées.

## See Also
- [about_Quoting_Rules](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_quoting_rules) - Règles de citation dans PowerShell.
- [about Automatic Variables](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_automatic_variables) - Pour en apprendre plus sur les variables automatiques de PowerShell.
- [String Formatting in PowerShell](https://ss64.com/ps/syntax-f-operator.html) - Plus d'infos sur la mise en forme de chaînes dans PowerShell.