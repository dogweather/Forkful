---
date: 2024-01-20 17:47:09.034892-07:00
description: "D\u0142ugo\u015B\u0107 ci\u0105gu to po prostu liczba znak\xF3w w tek\u015B\
  cie. Programi\u015Bci licz\u0105 znaki, by zarz\u0105dza\u0107 danymi - na przyk\u0142\
  ad sprawdzaj\u0105c has\u0142a czy ograniczaj\u0105c\u2026"
lastmod: '2024-03-13T22:44:35.399094-06:00'
model: gpt-4-1106-preview
summary: "D\u0142ugo\u015B\u0107 ci\u0105gu to po prostu liczba znak\xF3w w tek\u015B\
  cie."
title: "Znalezienie d\u0142ugo\u015Bci ci\u0105gu znak\xF3w"
weight: 7
---

## How to (Jak to zrobić):
W C# masz właściwość `Length` do liczenia znaków:

```C#
string przykladowyTekst = "Witaj świecie!";
int dlugosc = przykladowyTekst.Length;
Console.WriteLine("Długość stringa to: " + dlugosc);
```

Wyjście:

```
Długość stringa to: 14
```

## Deep Dive (W głębi tematu):
W C# `.Length` zwraca `int` reprezentujący liczbę `char` w stringu. Jest to szybka operacja, bo długość ciągu jest przechowywana wewnątrz obiektu `string`. W starszych wersjach języków, jak C, liczenie długości było bardziej skomplikowane, bo wymagało iteracji aż do napotkania znaku końca ciągu. Alternatywą dla `.Length` może być rozszerzenie LINQ, ale to zwykle mniej wydajne. Przy implementacji pamiętaj, że `string` w C# jest niezmienny i kodowanie Unicode może sprawiać, że nie zawsze licznik znaków odpowiada liczbie „widzialnych” symboli (na przykład ze względu na diakrytyki).

## See Also (Zobacz także):
- [Dokumentacja Microsoft dotycząca właściwości Length](https://docs.microsoft.com/en-us/dotnet/api/system.string.length)
- [Rozwinięcie tematu Unicode w C#](https://docs.microsoft.com/en-us/dotnet/standard/base-types/character-encoding)
- [Wprowadzenie do LINQ w C#](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/)
