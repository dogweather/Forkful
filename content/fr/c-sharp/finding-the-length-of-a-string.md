---
title:                "Trouver la longueur d'une chaîne de caractères"
aliases:
- fr/c-sharp/finding-the-length-of-a-string.md
date:                  2024-01-20T17:46:56.809897-07:00
model:                 gpt-4-1106-preview
simple_title:         "Trouver la longueur d'une chaîne de caractères"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/c-sharp/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
La longueur d'une chaîne, c'est combien de caractères elle contient. On mesure ça pour tout, des mots de passe aux tweets : c'est essentiel pour valider, stocker ou manipuler le texte.

## How to:
En C#, c'est simple. Utilisez la propriété `.Length` sur une chaîne pour obtenir sa longueur. Voici comment :

```C#
string salutation = "Bonjour";
int longueur = salutation.Length;
Console.WriteLine("La longueur de la chaîne est: " + longueur);
```

Sortie :

```
La longueur de la chaîne est: 7
```

## Deep Dive
Avant C#, on trouvait déjà la longueur des chaînes en C avec `strlen`, mais c'était moins sûr. En C#, la propriété `.Length` est rapide et sécurisée. Elle renvoie un `int` représentant le nombre de caractères `Char` dans la chaîne. Attention aux chaînes nulles : si vous appelez `.Length` sur `null`, vous aurez une `NullReferenceException`. Utilisez `?.Length` pour éviter ça avec sécurité :

```C#
string salutation = null;
int? longueur = salutation?.Length;
Console.WriteLine("La longueur de la chaîne est: " + (longueur.HasValue ? longueur.Value.ToString() : "null"));
```

Autres façons ? On pourrait penser à parcourir la chaîne avec une boucle, mais pourquoi réinventer la roue ? La propriété `.Length` est optimale et intégrée.

La norme Unicode pourrait être pertinente ici. `.Length` compte les unités de code UTF-16, pas les points de code ou les graphèmes. Donc pour des caractères composés ou spéciaux, `.Length` pourrait surpris.

## See Also
- Microsoft Docs sur les propriétés des chaînes en C# : https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/
- Unicode en détail : https://unicode.org/reports/tr29/
- Conseils sur la gestion des exceptions : https://docs.microsoft.com/en-us/dotnet/standard/exceptions/
