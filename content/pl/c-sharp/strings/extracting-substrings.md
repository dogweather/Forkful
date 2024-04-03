---
date: 2024-01-20 17:45:39.433286-07:00
description: "Wycinanie podci\u0105g\xF3w to odizolowanie wybranych cz\u0119\u015B\
  ci z wi\u0119kszego ci\u0105gu znak\xF3w. Robimy to, by manipulowa\u0107 danymi,\
  \ wyci\u0105ga\u0107 istotne informacje, czy\u2026"
lastmod: '2024-03-13T22:44:35.396562-06:00'
model: gpt-4-1106-preview
summary: "Wycinanie podci\u0105g\xF3w to odizolowanie wybranych cz\u0119\u015Bci z\
  \ wi\u0119kszego ci\u0105gu znak\xF3w."
title: "Wycinanie pod\u0142a\u0144cuch\xF3w"
weight: 6
---

## How to: (Jak to zrobić:)
```C#
using System;

class Program
{
    static void Main()
    {
        string fullText = "Cześć, jak się masz?";
        
        // Użyj 'Substring(startIndex, length)' do wycięcia "jak"
        string extracted = fullText.Substring(7, 3);
        Console.WriteLine(extracted);  // Output: jak

        // Użyj 'Substring(startIndex)' do wycięcia wszystkiego od "się"
        string remainingText = fullText.Substring(11);
        Console.WriteLine(remainingText);  // Output: się masz?
    }
}
```

## Deep Dive (Głębokie zanurzenie):
Wycinanie podciągów tekstowych nie zawsze było takie łatwe. Historia funkcji `Substring` w językach programowania pokazuje, jak wzrosło znaczenie prostoty i czytelności kodu. Alternatywnie, można użyć metod takich jak `Split`, `Remove`, `Replace`, czy LINQ, aby osiągnąć podobny efekt, ale z różnym stopniem kontroli i skomplikowania. W C#, `Substring` odwołuje się do znaków ciągu jako tablicy, ale z bezpieczeństwem typów i zarządzaniem pamięcią, tak, by operacje były zarówno wydajne, jak i bezpieczne.

## See Also (Zobacz także):
- [String.Substring Method in C# | Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/api/system.string.substring)
- [Manipulating Strings in C# | C# Fundamentals by Scott Allen](https://app.pluralsight.com/library/courses/csharp-fundamentals-dev/table-of-contents)
- [System.String | MSDN](https://msdn.microsoft.com/en-us/library/system.string(v=vs.110).aspx)
