---
title:                "Suppression de caractères correspondant à un motif"
aliases:
- /fr/c-sharp/deleting-characters-matching-a-pattern/
date:                  2024-01-20T17:41:49.575708-07:00
model:                 gpt-4-1106-preview
simple_title:         "Suppression de caractères correspondant à un motif"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/c-sharp/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Supprimer des caractères correspondant à un motif, c'est filtrer votre texte pour ne garder que l'essentiel. Les programmeurs font ça pour nettoyer des données, valider des entrées ou simplifier des chaînes.

## How to (Comment Faire ?)
Voici comment supprimer des caractères avec `Regex` en C# :

```C#
using System;
using System.Text.RegularExpressions;

class Program
{
    static void Main()
    {
        var phrase = "B0njour, C# 2023!";
        var motif = @"\d"; // Supprime tous les chiffres

        var resultat = Regex.Replace(phrase, motif, "");

        Console.WriteLine(resultat); // Affichera: Bonjour, C# !
    }
}
```
Sortie :
```
Bonjour, C# !
```

## Deep Dive (Plongée Profonde)
Historiquement, le traitement des chaînes de caractères est central dans la programmation. Les expressions régulières (RegEx) sont devenues un outil standard depuis les années 60 pour manipuler le texte. En C#, `System.Text.RegularExpressions` est le namespace à utiliser. Alternativement, on peut utiliser `String.Replace()` pour des remplacements simples ou LINQ pour des manipulations plus complexes. Concernant l'implémentation, `Regex.Replace()` est performant, mais attention à l'efficacité avec de grandes chaînes ou des motifs complexes.

## See Also (Voir Aussi)
- [Documentation Microsoft sur les expressions régulières en C#](https://docs.microsoft.com/fr-fr/dotnet/standard/base-types/regular-expressions)
- [Tutoriel sur les expressions régulières de Dot Net Perls](https://www.dotnetperls.com/regex)
- [Utilisation de LINQ pour manipuler des chaînes de caractères](https://docs.microsoft.com/fr-fr/dotnet/csharp/programming-guide/concepts/linq/)
