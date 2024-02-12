---
title:                "Analysering av HTML"
aliases:
- no/c-sharp/parsing-html.md
date:                  2024-02-03T19:11:52.140839-07:00
model:                 gpt-4-0125-preview
simple_title:         "Analysering av HTML"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/c-sharp/parsing-html.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Parsing av HTML i programmering innebærer å analysere strukturen til et HTML-dokument, noe som gjør det mulig for deg å trekke ut, manipulere og samhandle med innholdet programmatisk. Programmerere gjør dette for å automatisere webskraping, datautvinning, eller selv modifisere nettsider eller HTML-dokumenter dynamisk for ulike applikasjoner, noe som gjør det til en essensiell ferdighet innen webutvikling, dataanalyse og automatisert testing.

## Hvordan:

Selv om .NET gir grunnleggende støtte for å arbeide med HTML, slik som `HttpClient` for å hente websider, mangler det en innebygd, omfattende HTML-parser. Derfor vender de fleste C#-utviklere seg til populære tredjeparts biblioteker som HtmlAgilityPack eller AngleSharp for robuste HTML-parsingkapasiteter. Begge bibliotekene tillater enkel spørring, manipulering, og traversering av HTML-DOMen.

### Bruk av HtmlAgilityPack

1. **Installer HtmlAgilityPack**: Først, legg til HtmlAgilityPack-pakken i prosjektet ditt via NuGet.
   ```
   Install-Package HtmlAgilityPack
   ```

2. **Eksempelkode**: Parse en HTML-streng, og trekk ut titlene på alle `<h1>`-elementer.

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
                             <h1>Title 1</h1>
                             <h1>Title 2</h1>
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

   **Eksempel på utdata:**
   ```
   Title 1
   Title 2
   ```

### Bruk av AngleSharp

1. **Installer AngleSharp**: Legg til AngleSharp-biblioteket i prosjektet ditt gjennom NuGet.
   ```
   Install-Package AngleSharp
   ```

2. **Eksempelkode**: Last inn et HTML-dokument og spør etter `div`-elementer med en spesifikk klasse.

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
           var document = await context.OpenAsync(req => req.Content("<div class='item'>Item 1</div><div class='item'>Item 2</div>"));

           var items = document.QuerySelectorAll(".item").Select(element => element.TextContent);
           foreach (var item in items)
           {
               Console.WriteLine(item);
           }
       }
   }
   ```

   **Eksempel på utdata:**
   ```
   Item 1
   Item 2
   ```

Både HTMLAgilityPack og AngleSharp er kraftige verktøy for parsing av HTML, men ditt valg mellom dem kan avhenge av spesifikke prosjektkrav, ytelseshensyn, eller personlig preferanse i API-design.
