---
date: 2024-01-20 18:01:18.344600-07:00
description: "\xC5 sende en HTTP-foresp\xF8rsel med grunnleggende autentisering betyr\
  \ at du legger til et brukernavn og passord i foresp\xF8rselen for tilgangskontroll.\u2026"
lastmod: '2024-03-13T22:44:40.795428-06:00'
model: gpt-4-1106-preview
summary: "\xC5 sende en HTTP-foresp\xF8rsel med grunnleggende autentisering betyr\
  \ at du legger til et brukernavn og passord i foresp\xF8rselen for tilgangskontroll."
title: "\xC5 sende en HTTP-foresp\xF8rsel med grunnleggende autentisering"
weight: 45
---

## How to (Slik gjør du det)
```C#
using System;
using System.Net;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;

class BasicAuthExample
{
    static async Task Main()
    {
        var url = "https://example.com/api/data";
        var username = "brukernavn";
        var password = "passord";

        using (var httpClient = new HttpClient())
        {
            // Lager Base64-kodet streng av brukernavn og passord
            var credentials = Convert.ToBase64String(Encoding.ASCII.GetBytes($"{username}:{password}"));

            httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Basic", credentials);

            try
            {
                // Sender GET-forespørsel
                var response = await httpClient.GetAsync(url);
                var content = await response.Content.ReadAsStringAsync();

                Console.WriteLine("Status: " + response.StatusCode);
                Console.WriteLine("Innhold: ");
                Console.WriteLine(content);
            }
            catch (HttpRequestException e)
            {
                Console.WriteLine("Feil under forespørsel: " + e.Message);
            }
        }
    }
}
```

```C#
// Forventet output
Status: OK
Innhold: 
{ "eksempeldata": "verdi" }
```

## Deep Dive (Dypdykk)
Autentisering med Basic Auth er en enkel og historisk tidlig metode for å sikre HTTP-forespørsler, som legger til `Authorization`-headeren med brukernavn og passord kodet i Base64-format. Alternativer som OAuth er sikrere og mer komplekse. Basic Auth er greit for interne eller lavrisiko-applikasjoner, men bør unngås i produksjonsmiljøer som trenger sterk sikkerhet. Ved implementering, pass på at tilkoblingen bruker HTTPS for å forhindre utlevering av legitimasjon.

## See Also (Se også)
- [HttpClient Class Documentation](https://docs.microsoft.com/en-us/dotnet/api/system.net.http.httpclient)
- [AuthenticationHeaderValue Class Documentation](https://docs.microsoft.com/en-us/dotnet/api/system.net.http.headers.authenticationheadervalue)
- [Understanding Basic Authentication](https://www.ietf.org/rfc/rfc2617.txt)

Utforsk disse ressursene for å få en dypere forståelse og oppdag mer avanserte autentiseringsmetoder.
