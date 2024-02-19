---
aliases:
- /pt/c-sharp/parsing-html/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:11:43.733575-07:00
description: "Analisar HTML na programa\xE7\xE3o envolve analisar a estrutura de um\
  \ documento HTML, permitindo extrair, manipular e interagir com seu conte\xFAdo\
  \ de forma\u2026"
lastmod: 2024-02-18 23:08:58.155290
model: gpt-4-0125-preview
summary: "Analisar HTML na programa\xE7\xE3o envolve analisar a estrutura de um documento\
  \ HTML, permitindo extrair, manipular e interagir com seu conte\xFAdo de forma\u2026"
title: Analisando HTML
---

{{< edit_this_page >}}

## O Que & Por Quê?

Analisar HTML na programação envolve analisar a estrutura de um documento HTML, permitindo extrair, manipular e interagir com seu conteúdo de forma programática. Os programadores fazem isso para automatizar a raspagem da web, extração de dados, ou até mesmo modificar páginas da web ou documentos HTML dinamicamente para várias aplicações, tornando-se uma habilidade essencial no desenvolvimento web, análise de dados e cenários de testes automatizados.

## Como Fazer:

Embora o .NET forneça suporte básico para trabalhar com HTML, como o `HttpClient` para buscar páginas web, ele carece de um analisador HTML abrangente e integrado. Portanto, a maioria dos desenvolvedores C# recorre a bibliotecas de terceiros populares como HtmlAgilityPack ou AngleSharp para capacidades robustas de análise HTML. Ambas as bibliotecas permitem fácil consulta, manipulação e travessia do DOM HTML.

### Usando HtmlAgilityPack

1. **Instale o HtmlAgilityPack**: Primeiro, adicione o pacote HtmlAgilityPack ao seu projeto via NuGet.
   ```
   Install-Package HtmlAgilityPack
   ```

2. **Código de Exemplo**: Analise uma string HTML e extraia os títulos de todos os elementos `<h1>`.

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
                             <h1>Título 1</h1>
                             <h1>Título 2</h1>
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

   **Saída de Exemplo:**
   ```
   Título 1
   Título 2
   ```

### Usando AngleSharp

1. **Instale o AngleSharp**: Adicione a biblioteca AngleSharp ao seu projeto via NuGet.
   ```
   Install-Package AngleSharp
   ```

2. **Código de Exemplo**: Carregue um documento HTML e consulte elementos `div` com uma classe específica.

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

   **Saída de Exemplo:**
   ```
   Item 1
   Item 2
   ```

Tanto o HTMLAgilityPack quanto o AngleSharp são ferramentas poderosas para analisar HTML, mas sua escolha entre eles pode depender de requisitos específicos do projeto, considerações de desempenho ou preferência pessoal no design da API.
