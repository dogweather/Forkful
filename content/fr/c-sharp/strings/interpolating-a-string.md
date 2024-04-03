---
changelog:
- 2024-02-25, gpt-4-0125-preview, translated from English
date: 2024-02-25 17:06:53.132911-07:00
description: "L'interpolation de cha\xEEnes en C# vous permet de cr\xE9er une nouvelle\
  \ cha\xEEne en incluant des expressions \xE0 l'int\xE9rieur d'un litt\xE9ral de\
  \ cha\xEEne, facilitant\u2026"
lastmod: '2024-03-13T22:44:57.771945-06:00'
model: gpt-4-0125-preview
summary: "L'interpolation de cha\xEEnes en C# vous permet de cr\xE9er une nouvelle\
  \ cha\xEEne en incluant des expressions \xE0 l'int\xE9rieur d'un litt\xE9ral de\
  \ cha\xEEne, facilitant ainsi le formatage et la concat\xE9nation des cha\xEEnes."
title: "Interpolation d'une cha\xEEne de caract\xE8res"
weight: 8
---

## Comment faire :
En C#, l'interpolation de chaînes est indiquée par un signe dollar (`$`) suivi d'un littéral de chaîne. Les noms de variables ou les expressions sont inclus entre des accolades (`{}`).

```csharp
string name = "Jane";
int age = 28;
string interpolatedString = $"Bonjour, {name} ! Tu as {age} ans.";
Console.WriteLine(interpolatedString);
// Sortie : Bonjour, Jane ! Tu as 28 ans.
```

Dans un exemple plus complexe, vous pouvez effectuer des opérations ou appeler des méthodes à l'intérieur des accolades :

```csharp
double price = 19.99;
int quantity = 3;
string orderDetail = $"Prix total : {price * quantity:C2}";
Console.WriteLine(orderDetail);
// Sortie : Prix total : 59,97 $
```
Le spécificateur de format `:C2` à l'intérieur des accolades formate le nombre en tant que devise avec deux décimales.

Pour les scénarios nécessitant un formatage plus avancé ou une localisation, vous pourriez envisager d'utiliser la méthode `string.Format` ou des bibliothèques comme Humanizer. Humanizer peut manipuler et afficher des chaînes, des dates, des heures, des durées, des nombres et des quantités dans un format plus lisible pour l'humain. Ci-dessous un exemple d'utilisation de Humanizer pour une manipulation complexe de chaînes. Notez que Humanizer ne fait pas partie de la bibliothèque standard .NET et nécessite l'installation du package NuGet `Humanizer`.

Tout d'abord, installez Humanizer via NuGet :

```
Install-Package Humanizer
```

Ensuite, vous pouvez l'utiliser comme suit :

```csharp
using Humanizer;

int dayDifference = 5;
string humanized = $"L'événement a eu lieu il y a {dayDifference} jours.".Humanize();
Console.WriteLine(humanized);
// Selon la configuration et la culture, une sortie possible : L'événement a eu lieu il y a 5 jours.
```

Cet exemple démontre une utilisation de base. Humanizer prend en charge une large gamme de fonctionnalités qui peuvent être appliquées à des chaînes, des dates, des nombres et plus encore, rendant vos applications plus accessibles et intuitives.
