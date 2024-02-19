---
aliases:
- /no/kotlin/sending-an-http-request/
date: 2024-01-20 18:00:15.783024-07:00
description: "\xC5 sende en HTTP-foresp\xF8rsel betyr \xE5 be om data eller handling\
  \ fra en webserver. Programmerere gj\xF8r det for \xE5 integrere nettjenester og\
  \ hente data dynamisk."
lastmod: 2024-02-18 23:08:53.848891
model: gpt-4-1106-preview
summary: "\xC5 sende en HTTP-foresp\xF8rsel betyr \xE5 be om data eller handling fra\
  \ en webserver. Programmerere gj\xF8r det for \xE5 integrere nettjenester og hente\
  \ data dynamisk."
title: "\xC5 sende en HTTP-foresp\xF8rsel"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å sende en HTTP-forespørsel betyr å be om data eller handling fra en webserver. Programmerere gjør det for å integrere nettjenester og hente data dynamisk.

## Slik gjør du:
Kotlin gjør det enkelt med biblioteket `khttp`. Her er et eksempel for GET:

```Kotlin
import khttp.get

fun main() {
    val response = get("https://httpbin.org/get")
    println(response.text)
}
```

Resultat:

```
{
  "args": {}, 
  "headers": {
    "Accept-Encoding": "gzip, deflate", 
    "Host": "httpbin.org", 
    ...
  }, 
  ...
}
```

POST-forespørsel eksempel:

```Kotlin
import khttp.post

fun main() {
    val response = post(
        url = "https://httpbin.org/post",
        data = mapOf("key" to "value")
    )
    println(response.text)
}
```

Resultat:

```
{
  "args": {},
  "data": "",
  "files": {},
  "form": {
    "key": "value"
  },
  ...
}
```

## Dypdykk

HTTP-forespørslene begynte i tidlige nett-dager, grunnlagt for webkommunikasjon. Alternativer inkluderer WebSocket for toveiskommunikasjon, men for standard REST-kall er HTTP kongen.

Det er viktig å forstå HTTP-metoder: GET henter data; POST sender ny data; PUT oppdaterer eksisterende data; DELETE fjerner data. Kotlin-biblioteker som `khttp` og `Fuel` forenkler prosessen, men du kan også bruke Java-biblioteker som OkHttp eller Apache HttpClient.

Når du sender forespørsler i en mobil eller desktop-applikasjon, husk på nettverkstillatelser og asynkron behandling.

## Se også

- `khttp` dokumentasjon: https://khttp.readthedocs.io/en/latest/
- `Fuel` biblioteket for Kotlin: https://github.com/kittinunf/fuel
- OkHttp: https://square.github.io/okhttp/
- Apache HttpClient: https://hc.apache.org/httpcomponents-client-5.1.x/index.html
