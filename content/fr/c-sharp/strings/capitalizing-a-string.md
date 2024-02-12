---
title:                "Mettre en majuscule une chaîne"
aliases:
- /fr/c-sharp/capitalizing-a-string/
date:                  2024-02-03T19:05:17.483545-07:00
model:                 gpt-4-0125-preview
simple_title:         "Mettre en majuscule une chaîne"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/c-sharp/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Mettre en majuscule une chaîne de caractères en C# consiste à convertir le premier caractère d'une chaîne en majuscule s'il ne l'est pas déjà. Cette modification peut être cruciale pour formater les sorties, appliquer des normes de codage ou rendre les textes de l'interface utilisateur plus lisibles.

## Comment faire :
C# propose une approche simple pour mettre en majuscule les chaînes de caractères en utilisant des méthodes intégrées. La manière la plus simple d'y parvenir est de modifier directement la chaîne avec ces méthodes. Pour des règles de capitalisation plus complexes ou spécifiques (par exemple, mettre en majuscule chaque mot), des bibliothèques supplémentaires ou des méthodes manuelles peuvent être nécessaires. Ci-dessous, des exemples démontrent comment mettre en majuscule une chaîne de caractères de différentes manières en C#.

### Capitalisation de base :
Pour mettre en majuscule la première lettre d'un seul mot ou d'une phrase :

```csharp
string originalString = "hello world";
string capitalizedString = char.ToUpper(originalString[0]) + originalString.Substring(1);
Console.WriteLine(capitalizedString); // Sortie : "Hello world"
```

### Mettre en majuscule chaque mot :
Pour mettre en majuscule la première lettre de chaque mot dans une chaîne, vous pouvez utiliser la méthode `TextInfo.ToTitleCase` trouvée dans l'espace de noms `System.Globalization` :

```csharp
using System;
using System.Globalization;

string originalString = "hello world";
TextInfo textInfo = CultureInfo.CurrentCulture.TextInfo;
string capitalizedString = textInfo.ToTitleCase(originalString);
Console.WriteLine(capitalizedString); // Sortie : "Hello World"
```

Note : `ToTitleCase` ne transforme pas en minuscules les autres lettres ; elle ne change en majuscule que la première lettre de chaque mot. Aussi, certains mots dans les règles de majuscule (comme "and", "or", "of") peuvent ne pas être capitalisés en fonction des paramètres culturels.

### Utilisation des méthodes d'extension pour la réutilisabilité :
Vous pouvez créer une méthode d'extension pour la classe `string` afin de simplifier le processus de capitalisation, rendant votre code plus propre et réutilisable. Voici comment créer et utiliser une telle méthode :

```csharp
using System;

public static class StringExtensions
{
    public static string Capitalize(this string input)
    {
        if (string.IsNullOrEmpty(input))
        {
            return input;
        }
        return char.ToUpper(input[0]) + input.Substring(1);
    }
}

class Program
{
    static void Main(string[] args)
    {
        string originalString = "hello world";
        string capitalizedString = originalString.Capitalize();
        Console.WriteLine(capitalizedString); // Sortie : "Hello world"
    }
}
```

Cette méthode d'extension `Capitalize` peut être appelée sur n'importe quel objet de chaîne dans l'espace de noms, offrant une approche plus intuitive et orientée objet de la manipulation de chaînes en C#.

### Bibliothèques tierces :
Bien que la bibliothèque standard de C# couvre la plupart des besoins en matière de capitalisation de chaînes, certaines tâches spécialisées pourraient bénéficier de bibliothèques tierces, telles que Humanizer. Cependant, pour la tâche de simplement mettre en majuscule les chaînes ou chaque mot dans une chaîne, les méthodes standard de C# sont adéquates et efficaces, évitant ainsi le besoin de dépendances externes.
