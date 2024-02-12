---
title:                "Skicka en http-förfrågan"
aliases:
- /sv/ruby/sending-an-http-request/
date:                  2024-01-20T18:00:28.526973-07:00
model:                 gpt-4-1106-preview
simple_title:         "Skicka en http-förfrågan"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/ruby/sending-an-http-request.md"
---

{{< edit_this_page >}}

## What & Why? (Vad & Varför?)
Att skicka en HTTP-begäran innebär att din applikation eller skript gör en förfrågan till en webbserver för att hämta eller skicka information. Programmerare gör detta för att interagera med webbtjänster, API:er eller för att hämta data från internet.

## How to: (Hur man gör:)
För att skicka en HTTP-förfrågan i Ruby, kan man använda `net/http` biblioteket som är inbyggt. Här är ett enkelt exempel på en GET-förfrågan:

```ruby
require 'net/http'
require 'uri'

uri = URI('http://example.com/')
response = Net::HTTP.get_response(uri)

puts response.body if response.is_a?(Net::HTTPSuccess)
```

Om du kör detta skript får du HTML-innehållet i `http://example.com/`.

## Deep Dive (Djupdykning)
HTTP-förfrågningar är fundamentet för webbkommunikation, introducerade i början av webbens historia. Förutom `net/http`, finns det andra alternativ i Ruby som `httparty` eller `faraday`, vilka kan erbjuda mer funktionalitet och användarvänlighet.

`Net::HTTP` är en lågnivå-klass som hanterar HTTP-kommunikation. Medan den ger mycket kontroll, kan den vara omständlig för avancerade förfrågningar. `HTTParty` och `Faraday` är högnivå-alternativ som kan hantera komplexa förfrågningar och middleware, vilket gör dem till ett populärt val i Ruby-communityn.

När man bygger en förfrågan, är det viktigt att tänka på HTTP-metoder (GET, POST, PUT, DELETE etc.), samt statuskoder som indikerar resultatet av förfrågan (200 för framgång, 404 för hittas inte, etc.). Autentisering och headers kan också behöva inkluderas beroende på API:ets krav.

## See Also (Se Även)
- Ruby's Net::HTTP dokumentation: [https://ruby-doc.org/stdlib-2.7.1/libdoc/net/http/rdoc/Net/HTTP.html](https://ruby-doc.org/stdlib-2.7.1/libdoc/net/http/rdoc/Net/HTTP.html)
- HTTParty GitHub repo: [https://github.com/jnunemaker/httparty](https://github.com/jnunemaker/httparty)
- Faraday GitHub repo: [https://github.com/lostisland/faraday](https://github.com/lostisland/faraday)
- En introduktion till HTTP-statuskoder: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
