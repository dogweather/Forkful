---
date: 2024-01-20 17:59:51.773352-07:00
description: "Wysy\u0142anie \u017C\u0105dania HTTP to spos\xF3b, w jaki Tw\xF3j program\
  \ mo\u017Ce komunikowa\u0107 si\u0119 z serwerem w internecie, np. aby pobra\u0107\
  \ dane lub wys\u0142a\u0107 informacje. Programi\u015Bci\u2026"
lastmod: '2024-03-13T22:44:35.448371-06:00'
model: gpt-4-1106-preview
summary: "Wysy\u0142anie \u017C\u0105dania HTTP to spos\xF3b, w jaki Tw\xF3j program\
  \ mo\u017Ce komunikowa\u0107 si\u0119 z serwerem w internecie, np."
title: "Wysy\u0142anie \u017C\u0105dania HTTP"
weight: 44
---

## Jak to zrobić:
W Haskellu do wysyłania żądań HTTP możemy użyć biblioteki `http-conduit`. Poniżej znajdziesz przykład prostego żądania GET.

```haskell
import Network.HTTP.Simple

main :: IO ()
main = do
    response <- httpBS "http://httpbin.org/get"
    putStrLn $ "The status code was: " ++ show (getResponseStatusCode response)
    putStrLn "The headers were:"
    print $ getResponseHeaders response
    putStrLn "The body was:"
    BS.putStrLn $ getResponseBody response
```

Przy uruchomieniu, wynik będzie podobny do poniższego:

```
The status code was: 200
The headers were:
[(CI.mk "Content-Type","application/json"), ...]
The body was:
{
  ...
}
```

## Deep Dive
W roku 2011, HTTP Conduit został stworzony jako część większej biblioteki `conduit` dla języka Haskell, ułatwiająca obsługę strumieni danych. Alternatywami dla `http-conduit` mogą być `http-client` lub bardziej niskopoziomowa `http` - ale `conduit` oferuje dużą elastyczność, zwłaszcza przy obsłudze dużych danych.

Podczas wysyłania zapytania, `http-conduit` tworzy połączenie z podanym URL, wysyła żądanie i czeka na odpowiedź. Jest to asynchroniczna operacja, która w Haskellu jest obsługiwana za pomocą monad IO, pozwalając na efekty uboczne w czysto funkcyjnym środowisku.

Alternatywne biblioteki jak `Wreq` lub `Req` też pozwalają na wysyłanie żądań HTTP, często z dodatkowymi udogodnieniami typu automatyczne przetwarzanie JSON, ale mogą być mniej elastyczne przy pracy ze specyficznymi rodzajami powiązań HTTP.

## See Also
- Biblioteka `http-conduit`: https://www.stackage.org/package/http-conduit
- Dokumentacja `http-client`, której `http-conduit` używa: https://www.stackage.org/package/http-client
- `conduit` tutorial, pokazujący jak zarządzać strumieniami danych: https://www.yesodweb.com/book/conduit
- Porównanie bibliotek HTTP dla Haskell: https://wiki.haskell.org/Network_programming#Libraries_for_HTTP_client_programming
