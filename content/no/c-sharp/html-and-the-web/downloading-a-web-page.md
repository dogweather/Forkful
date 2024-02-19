---
aliases:
- /no/c-sharp/downloading-a-web-page/
date: 2024-01-20 17:43:47.162005-07:00
description: "Nedlasting av en nettside betyr at du henter ned HTML innholdet fra\
  \ en nettadresse. Programmerere gj\xF8r dette for \xE5 bearbeide data, skrape informasjon,\u2026"
lastmod: 2024-02-18 23:08:53.892639
model: gpt-4-1106-preview
summary: "Nedlasting av en nettside betyr at du henter ned HTML innholdet fra en nettadresse.\
  \ Programmerere gj\xF8r dette for \xE5 bearbeide data, skrape informasjon,\u2026"
title: Nedlasting av en nettside
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Nedlasting av en nettside betyr at du henter ned HTML innholdet fra en nettadresse. Programmerere gjør dette for å bearbeide data, skrape informasjon, eller sjekke nettsidens tilgjengelighet.

## Hvordan:
For å laste ned en nettside i C#, kan du bruke `HttpClient`. Her er en kjapp og skitten måte å gjøre det på:

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (HttpClient client = new HttpClient())
        {
            HttpResponseMessage response = await client.GetAsync("https://www.example.com");
            if (response.IsSuccessStatusCode)
            {
                string content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content.Substring(0, 200)); // Skriver ut de første 200 tegnene for brevhet
            }
            else
            {
                Console.WriteLine("Kunne ikke laste ned siden: " + response.StatusCode);
            }
        }
    }
}
```

Kjører du koden, får du første delen av HTML innholdet til 'example.com' skrevet ut i konsollen.

## Dypdykk:
Nedlasting av nettsider i C# har utviklet seg. Før `HttpClient`, brukte vi `WebClient` og før det `HttpWebRequest`. `HttpClient` er nå anbefalt for sin ytelse og brukervennlighet. Alternativer eksisterer, som `RestSharp` for REST API-er eller `HtmlAgilityPack` for HTML parsing.

I tillegg til metoden vist ovenfor, har `HttpClient` flere innstillinger for timeout, headers, og til og med hendelser for å overvåke progressjonen på store nedlastinger. For skalerbarhet og responsivitet, bruk `async` og `await` nøkkelordene for ikke å blokkere UI tråden eller skape unødvendig ventetid.

## Se Også:
- [HttpClient Class](https://docs.microsoft.com/en-us/dotnet/api/system.net.http.httpclient?view=net-6.0)
- [Making HTTP Requests in .NET](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient)
- [Async and Await](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/)
