---
aliases:
- /pl/c-sharp/starting-a-new-project/
date: 2024-01-20 18:03:05.413806-07:00
description: "Zaczynamy nowy projekt, gdy mamy \u015Bwie\u017Cy pomys\u0142 lub potrzeb\u0119\
  \ rozwi\u0105zania. Programi\u015Bci robi\u0105 to, aby przekszta\u0142ci\u0107\
  \ koncepcje w dzia\u0142aj\u0105ce aplikacje, ucz\u0105c\u2026"
lastmod: 2024-02-18 23:08:49.611301
model: gpt-4-1106-preview
summary: "Zaczynamy nowy projekt, gdy mamy \u015Bwie\u017Cy pomys\u0142 lub potrzeb\u0119\
  \ rozwi\u0105zania. Programi\u015Bci robi\u0105 to, aby przekszta\u0142ci\u0107\
  \ koncepcje w dzia\u0142aj\u0105ce aplikacje, ucz\u0105c\u2026"
title: Rozpoczynanie nowego projektu
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Zaczynamy nowy projekt, gdy mamy świeży pomysł lub potrzebę rozwiązania. Programiści robią to, aby przekształcić koncepcje w działające aplikacje, ucząc się po drodze nowych rzeczy i udoskonalając swoje umiejętności.

## How to: (Jak to zrobić:)
```C#
// Tworzenie nowego projektu konsoli w C# z użyciem .NET CLI
// Otwórz terminal i wpisz:
dotnet new console -o MojaAplikacja

// Przejdź do katalogu projektu:
cd MojaAplikacja

// Uruchom aplikację:
dotnet run

// Powinieneś zobaczyć:
Hello, World!
```

## Deep Dive (Dogłębna Analiza)
Historia narzędzi tworzenia projektów w C# sięga IDE Microsoft Visual Studio, które zrewolucjonizowało sposób, w jaki deweloperzy rozpoczynają prace. Alternatywą dla linii poleceń jest właśnie Visual Studio, gdzie nowy projekt tworzy się przez wizualne interfejsy.

W CLI (.NET Core CLI, obecnie po prostu .NET CLI) używamy `dotnet new` z odpowiednimi szablonami. Dla konkretnych rodzajów projektów (np. aplikacje webowe, biblioteki klas) są inne szablony. Warto też wspomnieć o opcjach konfiguracyjnych dostępnych w pliku projektu (.csproj), które umożliwiają szczegółowe dostosowanie budowania i uruchamiania projektu.

Podczas tworzenia projektu ważne jest zrozumienie struktury folderów i plików oraz konwencji nazewnictwa. Jeśli dobrze zorganizujemy projekt na początku, łatwiej będzie go rozwijać.

## See Also (Zobacz Również)
- [Dokumentacja .NET CLI](https://docs.microsoft.com/pl-pl/dotnet/core/tools/)
- [C# Programming Guide (Przewodnik programowania w C#)](https://docs.microsoft.com/pl-pl/dotnet/csharp/programming-guide/)
