---
aliases:
- /it/haskell/sending-an-http-request/
date: 2024-01-20 17:59:38.970846-07:00
description: "Mandare una richiesta HTTP significa ordinare al tuo programma di chiacchierare\
  \ con un server web. Questo lo fanno i programmatori per scambiare dati -\u2026"
lastmod: 2024-02-18 23:08:55.927112
model: gpt-4-1106-preview
summary: "Mandare una richiesta HTTP significa ordinare al tuo programma di chiacchierare\
  \ con un server web. Questo lo fanno i programmatori per scambiare dati -\u2026"
title: Inviare una richiesta http
---

{{< edit_this_page >}}

## What & Why?
Mandare una richiesta HTTP significa ordinare al tuo programma di chiacchierare con un server web. Questo lo fanno i programmatori per scambiare dati - pensa a scaricare una pagina web o a inviare un form.

## How to:
In Haskell, usiamo librerie come `http-conduit` per mandare richieste HTTP. Ecco un esempio veloce:

```haskell
import Network.HTTP.Simple

main :: IO ()
main = do
    response <- httpBS "http://httpbin.org/get"
    putStrLn $ "The status code was: " ++ show (getResponseStatusCode response)
    print $ getResponseHeader "Content-Type" response
    putStrLn $ "The body is: " ++ show (getResponseBody response)
```

Se avvii questo codice, otterrai qualcosa del tipo:

```
The status code was: 200
["application/json"]
The body is: "<qui ci sarà il corpo della risposta>"
```

## Deep Dive
Haskell, bello e funzionale, non è stato il primo a fare richieste HTTP. Questo esiste da quando internet ha avuto bisogno di comunicare a distanza. Le alternative includono librerie come `Network.HTTP` o `wget` via `System.Process`. Quando invii una richiesta, sotto il cofano, la libreria gestisce la connessione TCP/IP, costruendo l'header HTTP e interpretando la risposta.

## See Also
- La documentazione di [`http-conduit`](https://hackage.haskell.org/package/http-conduit)
- Tutorial Haskell su richieste HTTP: [School of Haskell](https://www.schoolofhaskell.com)
- Leggi sulla [`Network.HTTP`](https://hackage.haskell.org/package/HTTP) library per un'altra prospettiva
