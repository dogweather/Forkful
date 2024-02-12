---
title:                "Tolka HTML"
aliases:
- /sv/c-sharp/parsing-html/
date:                  2024-02-03T19:11:42.257455-07:00
model:                 gpt-4-0125-preview
simple_title:         "Tolka HTML"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/c-sharp/parsing-html.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

Att tolka HTML i programmering innebär att analysera en HTML-dokuments struktur, vilket möjliggör för dig att extrahera, manipulera och interagera med dess innehåll programmatiskt. Programmerare gör detta för att automatisera webbskrapning, dataextraktion eller till och med modifiera webbsidor eller HTML-dokument dynamiskt för olika applikationer, vilket gör det till en viktig färdighet inom webbutveckling, dataanalys och automatiska testningsscenarier.

## Hur:

Medan .NET tillhandahåller grundläggande stöd för att arbeta med HTML, som `HttpClient` för att hämta webbsidor, saknar det en inbyggd, omfattande HTML-tolk. Därför vänder sig de flesta C#-utvecklare till populära tredjepartsbibliotek som HtmlAgilityPack eller AngleSharp för robusta funktioner för HTML-tolkning. Båda biblioteken tillåter lätt frågeställning, manipulation och traversal av HTML DOM.

### Använda HtmlAgilityPack

1. **Installera HtmlAgilityPack**: Lägg först till HtmlAgilityPack-paketet i ditt projekt via NuGet.
   ```
   Install-Package HtmlAgilityPack
   ```

2. **Exempelkod**: Tolka en HTML-sträng och extrahera titlarna på alla `<h1>`-element.

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
                             <h1>Titel 1</h1>
                             <h1>Titel 2</h1>
                         </body>
                        </html>";
           var htmlDoc = new HtmlDocument();
           htmlDoc.LoadHtml(html);

           var h1Taggar = htmlDoc.DocumentNode.SelectNodes("//h1").Select(node => node.InnerText);
           foreach (var titel in h1Taggar)
           {
               Console.WriteLine(titel);
           }
       }
   }
   ```

   **Exempelutskrift:**
   ```
   Titel 1
   Titel 2
   ```

### Använda AngleSharp

1. **Installera AngleSharp**: Lägg till AngleSharp-biblioteket i ditt projekt via NuGet.
   ```
   Install-Package AngleSharp
   ```

2. **Exempelkod**: Ladda ett HTML-dokument och fråga efter `div`-element med en specifik klass.

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
           var document = await context.OpenAsync(req => req.Content("<div class='item'>Artikel 1</div><div class='item'>Artikel 2</div>"));

           var artiklar = document.QuerySelectorAll(".item").Select(element => element.TextContent);
           foreach (var artikel in artiklar)
           {
               Console.WriteLine(artikel);
           }
       }
   }
   ```

   **Exempelutskrift:**
   ```
   Artikel 1
   Artikel 2
   ```

Både HTMLAgilityPack och AngleSharp är kraftfulla verktyg för att tolka HTML, men ditt val mellan dem kan bero på specifika projektbehov, prestandaöverväganden eller personliga preferenser i API-design.
