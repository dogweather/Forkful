---
date: 2024-01-20 18:01:50.047790-07:00
description: "Att skicka en HTTP-f\xF6rfr\xE5gan med grundl\xE4ggande autentisering\
  \ inneb\xE4r att du inkluderar anv\xE4ndarnamn och l\xF6senord i f\xF6rfr\xE5gningen\
  \ f\xF6r att f\xE5 tillg\xE5ng till\u2026"
lastmod: '2024-03-13T22:44:37.954881-06:00'
model: gpt-4-1106-preview
summary: "Att skicka en HTTP-f\xF6rfr\xE5gan med grundl\xE4ggande autentisering inneb\xE4\
  r att du inkluderar anv\xE4ndarnamn och l\xF6senord i f\xF6rfr\xE5gningen f\xF6\
  r att f\xE5 tillg\xE5ng till skyddad data."
title: "Skicka en HTTP-f\xF6rfr\xE5gan med Basic-autentisering"
weight: 45
---

## Hur man gör:
Här är ett exempel i Haskell med `http-client` och `base64-bytestring` för att skicka en HTTP GET-förfrågan med grundläggande autentisering:

```Haskell
import Network.HTTP.Client
import Network.HTTP.Types.Header (hAuthorization)
import Data.ByteString.Base64 (encode)
import Data.ByteString.Char8 (pack, append)

-- Konfigurera HTTP-manager
manager <- newManager defaultManagerSettings

-- Bygg URL och autentiseringsuppgifter
let url = "https://example.com/api/data"
let credentials = "användarnamn:lösenord"
let authHeader = "Basic " `append` (encode . pack $ credentials)

-- Skapa förfrågan och inkludera autentiseringsheader
request <- parseRequest url
let requestWithAuth = request { requestHeaders = [(hAuthorization, authHeader)] }

-- Skicka förfrågan och få svar
response <- httpLbs requestWithAuth manager

-- Skriv ut svaret
putStrLn $ show (responseBody response)
```

I det här exemplet ska du ersätta `"användarnamn:lösenord"` med dina faktiska autentiseringsuppgifter. Efter att ha kört koden bör du se svaret från servern. Kom ihåg att hålla dina autentiseringsuppgifter säkra!

## Fördjupning
Grundläggande autentisering är en del av HTTP-protokollet sedan det skapades på 90-talet. Det är inte den säkraste metoden men det är lätt att implementera och fungerar därför bra för enklare use cases eller interna nätverk.

Alternativ till grundläggande autentisering inkluderar OAuth och API-nycklar, som båda erbjuder högre säkerhetsnivåer. I Haskell kan du använda bibliotek som `wreq` eller `http-conduit` för flexibilitet och fler autentiseringsmetoder.

En viktig detalj när du använder grundläggande autentisering är att alltid använda HTTPS för att förhindra att din trafik avlyssnas. Att skicka autentiseringsuppgifter okrypterat över HTTP är en stor säkerhetsrisk.

## Se Även
- HTTP-client dokumentation: https://hackage.haskell.org/package/http-client
- Base64-bytestring dokumentation: https://hackage.haskell.org/package/base64-bytestring
- Hur man arbetar säkert med HTTP i Haskell: https://www.yesodweb.com/book/http-client
