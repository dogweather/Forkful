---
title:                "Inviare una richiesta http con autenticazione di base"
aliases:
- /it/haskell/sending-an-http-request-with-basic-authentication/
date:                  2024-01-20T18:01:55.842721-07:00
model:                 gpt-4-1106-preview
simple_title:         "Inviare una richiesta http con autenticazione di base"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/haskell/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why?
L'autenticazione di base HTTP è un metodo per inviare le credenziali (username e password) in un'intestazione HTTP. I programmatori la utilizzano per accedere a server e servizi web che richiedono identificazione.

## How to:
Per eseguire una richiesta HTTP con autenticazione di base in Haskell, utilizziamo la libreria `http-conduit`. Installala con `cabal install http-conduit`.

```Haskell
import Network.HTTP.Simple
import Network.HTTP.Types.Header (hAuthorization)
import Data.ByteString.Base64 (encode)
import qualified Data.ByteString.Char8 as BS

main :: IO ()
main = do
  let username = "utente"
  let password = "secret"
  let auth = BS.concat ["Basic ", encode (BS.concat [username, ":", password])]
  
  request' <- parseRequest "http://esempio.com/dati"
  let request = setRequestHeader hAuthorization [auth] request'

  response <- httpLBS request
  putStrLn $ "Status code: " ++ show (getResponseStatusCode response)
  print $ getResponseBody response
```

Esegui e vedi il risultato, che includerà il codice di stato e il contenuto della risposta.

## Deep Dive
L'autenticazione HTTP di base esiste dagli inizi del web. Sebbene non sia la più sicura (le credenziali sono codificate in Base64 ma non criptate), è semplice da implementare. Oggi, sarebbe meglio usare alternative come l'autenticazione OAuth. In Haskell, le richieste HTTP sfruttano le librerie come `http-conduit`, che gestiscono dettagli basso-livello come la connessione di rete e l'elaborazione delle risposte.

## See Also
- `http-conduit` documentation: [https://hackage.haskell.org/package/http-conduit](https://hackage.haskell.org/package/http-conduit)
- HTTP Basic Authentication on MDN: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#basic_authentication_scheme](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#basic_authentication_scheme)
- Alternative Auth Methods – OAuth: [https://oauth.net/](https://oauth.net/)
