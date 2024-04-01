---
date: 2024-01-26 03:47:54.214516-07:00
description: "Utiliser un d\xE9bogueur signifie avoir recours \xE0 des outils sp\xE9\
  cialis\xE9s pour tester et diagnostiquer du code. Les programmeurs le font pour\
  \ \xE9liminer les\u2026"
lastmod: '2024-03-13T22:44:57.792360-06:00'
model: gpt-4-0125-preview
summary: "Utiliser un d\xE9bogueur signifie avoir recours \xE0 des outils sp\xE9cialis\xE9\
  s pour tester et diagnostiquer du code. Les programmeurs le font pour \xE9liminer\
  \ les\u2026"
title: "Utilisation d'un d\xE9bogueur"
---

## Comment faire:
Imaginez que vous avez un petit programme qui ne fonctionne pas correctement :

```C#
static void Main()
{
    int result = Sum(1, 2);
    Console.WriteLine(result);
}

static int Sum(int a, int b)
{
    return a + a; // Oups, devrait être a + b
}
```

En utilisant le débogueur de Visual Studio, définissez un point d'arrêt en cliquant sur la marge de gauche à côté de `return a + a;`. Lorsque vous exécutez le programme (avec F5), l'exécution s'arrêtera là. Survolez les variables pour inspecter leurs valeurs, ou utilisez la fenêtre Immédiate pour évaluer des expressions. Vous verrez que `a` est 1 et `b` est 2, mais `a + a` n'est pas notre somme attendue. Modifiez-le pour `a + b`, continuez l'exécution (F5), et voilà, la console affiche 3.

## Approfondissement
L'histoire du débogage remonte aux années 1940, lorsqu'un véritable bug (un papillon) a été trouvé dans un ordinateur primitif. Les débogueurs d'aujourd'hui, comme celui de Visual Studio, offrent une suite de fonctionnalités puissantes, incluant les points d'arrêt, l'exécution pas à pas, les fenêtres d'observation, et plus encore.

Parmi les alternatives au débogueur de Visual Studio, il y a des options open-source comme GDB pour les langages de style C ou pdb pour Python, et des IDE multiplateformes comme JetBrains Rider ou VS Code qui proposent des outils de débogage pour C# et d'autres langages.

Lorsque vous plongez dans l'implémentation d'un débogueur, vous examinez un programme qui se connecte au processus de votre application. Il interprète le code machine, gère l'état de la mémoire et contrôle le flux d'exécution. C'est du lourd qui est crucial pour un débogage efficace, c'est pourquoi le mode débogage est souvent plus lent que le mode de lancement où ces crochets n'existent pas.

## Voir également
- [Documentation du débogueur Visual Studio](https://docs.microsoft.com/en-us/visualstudio/debugger/)
- [Stratégies de débogage](https://www.codeproject.com/Articles/79508/Effective-Exception-Handling-in-Visual-C)
