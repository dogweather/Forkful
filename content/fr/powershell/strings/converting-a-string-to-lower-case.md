---
date: 2024-01-20 17:39:04.181923-07:00
description: "Convertir une cha\xEEne en minuscules, c'est passer tous ses caract\xE8\
  res en minuscules. Les d\xE9veloppeurs font \xE7a pour uniformiser les donn\xE9\
  es, faciliter les\u2026"
lastmod: '2024-03-13T22:44:58.029674-06:00'
model: gpt-4-1106-preview
summary: "Convertir une cha\xEEne en minuscules, c'est passer tous ses caract\xE8\
  res en minuscules."
title: "Conversion d'une cha\xEEne de caract\xE8res en minuscules"
weight: 4
---

## How to: / Comment faire :
```PowerShell
# Transformer une chaîne en minuscules
$chaine = "Bonjour, je suis en MAJUSCULES!"
$chaine.ToLower()

# Résultat
bonjour, je suis en majuscules!
```

## Deep Dive / Plongée Profonde
Historiquement, convertir une chaîne en minuscules est fondamental en informatique pour les manipulations de textes. PowerShell utilise la méthode `.ToLower()` héritée de .NET pour réaliser cette tâche. Certains langages utilisent des fonctions telles que `strtolower()` en PHP ou `lower()` en Python.

En PowerShell, la méthode `.ToLower()` est culturellement neutre par défaut, utilisant les conventions de minuscules invariantes. Mais vous pouvez passer une culture spécifique si besoin, par exemple `.ToLower('fr-FR')` pour la culture française.

Alternativement, PowerShell 7+ propose l'opérateur `-ceq` pour effectuer une comparaison de chaînes sans tenir compte de la casse, sans avoir à changer la casse des chaînes en premier lieu.

En termes d'implémentation, considerer les variations linguistiques peut être important; certaines langues ont des règles spécifiques pour la casse des caractères.

## See Also / Voir Aussi
- [Documentation officielle de PowerShell](https://docs.microsoft.com/powershell/)
- [CultureInfo Class in .NET](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo)

N'oubliez pas de valider votre code dans plusieurs scénarios et cultures!
