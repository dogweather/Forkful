---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:33:20.828476-07:00
description: "Pisanie do standardowego b\u0142\u0119du (stderr) w Haskellu pozwala\
  \ programom rozr\xF3\u017Cnia\u0107 ich wyj\u015Bcie pomi\u0119dzy normalnymi wynikami\
  \ a komunikatami o b\u0142\u0119dach. Jest to\u2026"
lastmod: '2024-03-13T22:44:35.469245-06:00'
model: gpt-4-0125-preview
summary: "Pisanie do standardowego b\u0142\u0119du (stderr) w Haskellu pozwala programom\
  \ rozr\xF3\u017Cnia\u0107 ich wyj\u015Bcie pomi\u0119dzy normalnymi wynikami a komunikatami\
  \ o b\u0142\u0119dach."
title: "Pisanie do standardowego b\u0142\u0119du"
weight: 25
---

## Jak to zrobić:
W Haskellu, pisanie do stderr jest proste dzięki modułowi `System.IO` z biblioteki podstawowej. Poniżej znajduje się podstawowy przykład demonstrujący:

```haskell
import System.IO

main :: IO ()
main = do
  hPutStrLn stderr "To jest komunikat o błędzie."
```

Wyjście tego programu do stderr będzie:

```
To jest komunikat o błędzie.
```

Jeśli pracujesz nad bardziej złożoną aplikacją, lub jeśli potrzebujesz lepszej kontroli nad logowaniem (w tym błędów), możesz optować za użyciem biblioteki stron trzecich. Jednym z popularnych wyborów jest `monad-logger`, który integruje się ze stylem programowania `mtl` w Haskellu. Oto mały fragment używający `monad-logger`:

```haskell
{-# LANGUAGE OverloadedStrings #-}
import Control.Monad.Logger

main :: IO ()
main = runStderrLoggingT $ do
  logErrorN "To jest komunikat o błędzie używając monad-logger."
```

Kiedy uruchomiony, wersja `monad-logger` podobnie wypisuje komunikat o błędzie, ale jest wyposażona w więcej kontekstu, jak znaczniki czasu czy poziomy logowania, w zależności od konfiguracji:

```
[Error] To jest komunikat o błędzie używając monad-logger.
```

Obie metody służą celowi pisania do stderr, z wyborem w dużej mierze zależnym od złożoności i potrzeb twojej aplikacji.
