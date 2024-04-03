---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:11:57.411408-07:00
description: "Parsowanie HTML w programowaniu polega na analizie struktury dokumentu\
  \ HTML, co pozwala na ekstrakcj\u0119, manipulacj\u0119 i interakcj\u0119 z jego\
  \ zawarto\u015Bci\u0105\u2026"
lastmod: '2024-03-13T22:44:35.406212-06:00'
model: gpt-4-0125-preview
summary: "Parsowanie HTML w programowaniu polega na analizie struktury dokumentu HTML,\
  \ co pozwala na ekstrakcj\u0119, manipulacj\u0119 i interakcj\u0119 z jego zawarto\u015B\
  ci\u0105 programowo."
title: "Analiza sk\u0142adniowa HTML"
weight: 43
---

## Jak to zrobić:
Chociaż .NET oferuje podstawowe wsparcie dla pracy z HTML, takie jak `HttpClient` do pobierania stron internetowych, brakuje mu wbudowanego, kompleksowego parsera HTML. Dlatego większość programistów C# zwraca się do popularnych bibliotek stron trzecich, takich jak HtmlAgilityPack lub AngleSharp, dla solidnych możliwości parsowania HTML. Obie biblioteki umożliwiają łatwe zapytania, manipulację i przeglądanie obiektowego modelu dokumentu (DOM) HTML.

### Korzystanie z HtmlAgilityPack
1. **Zainstaluj HtmlAgilityPack**: Najpierw dodaj pakiet HtmlAgilityPack do swojego projektu za pomocą NuGet.
   ```
   Install-Package HtmlAgilityPack
   ```

2. **Przykładowy kod**: Zanalizuj ciąg HTML i wydobyj tytuły wszystkich elementów `<h1>`.

   ```csharp
   using HtmlAgilityPack;
   using System;
   using System.Linq;

   class Program
   {
       static void Main(string[] args)
       {
           var html = @"<html>
                         <body>
                             <h1>Tytuł 1</h1>
                             <h1>Tytuł 2</h1>
                         </body>
                        </html>";
           var htmlDoc = new HtmlDocument();
           htmlDoc.LoadHtml(html);

           var h1Tags = htmlDoc.DocumentNode.SelectNodes("//h1").Select(node => node.InnerText);
           foreach (var title in h1Tags)
           {
               Console.WriteLine(title);
           }
       }
   }
   ```

   **Przykładowe wyjście:**
   ```
   Tytuł 1
   Tytuł 2
   ```

### Korzystanie z AngleSharp
1. **Zainstaluj AngleSharp**: Dodaj bibliotekę AngleSharp do swojego projektu za pomocą NuGet.
   ```
   Install-Package AngleSharp
   ```

2. **Przykładowy kod**: Załaduj dokument HTML i wyszukaj elementy `div` z określoną klasą.

   ```csharp
   using AngleSharp;
   using AngleSharp.Dom;
   using System;
   using System.Linq;
   using System.Threading.Tasks;

   class Program
   {
       static async Task Main(string[] args)
       {
           var context = BrowsingContext.New(Configuration.Default);
           var document = await context.OpenAsync(req => req.Content("<div class='item'>Przedmiot 1</div><div class='item'>Przedmiot 2</div>"));

           var items = document.QuerySelectorAll(".item").Select(element => element.TextContent);
           foreach (var item in items)
           {
               Console.WriteLine(item);
           }
       }
   }
   ```

   **Przykładowe wyjście:**
   ```
   Przedmiot 1
   Przedmiot 2
   ```

Zarówno HTMLAgilityPack, jak i AngleSharp, to potężne narzędzia do parsowania HTML, ale wybór między nimi może zależeć od konkretnych wymagań projektowych, względów wydajnościowych lub osobistych preferencji w zakresie projektowania API.
