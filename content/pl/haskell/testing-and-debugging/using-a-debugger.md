---
aliases:
- /pl/haskell/using-a-debugger/
date: 2024-01-26 03:49:52.159715-07:00
description: "Korzystanie z debugera oznacza zag\u0142\u0119bianie si\u0119 w Tw\xF3\
  j kod przy u\u017Cyciu narz\u0119dzi zaprojektowanych do inspekcji, wstrzymywania\
  \ i manipulowania programem w\u2026"
lastmod: 2024-02-18 23:08:49.657775
model: gpt-4-0125-preview
summary: "Korzystanie z debugera oznacza zag\u0142\u0119bianie si\u0119 w Tw\xF3j\
  \ kod przy u\u017Cyciu narz\u0119dzi zaprojektowanych do inspekcji, wstrzymywania\
  \ i manipulowania programem w\u2026"
title: Korzystanie z debugera
---

{{< edit_this_page >}}

## Co i Dlaczego?
Korzystanie z debugera oznacza zagłębianie się w Twój kod przy użyciu narzędzi zaprojektowanych do inspekcji, wstrzymywania i manipulowania programem w trakcie jego wykonania. Programiści robią to, aby śledzić błędy, rozumieć przepływ programu i upewnić się, że ich kod robi dokładnie to, czego oczekują.

## Jak to zrobić:
Wybierzmy się na spacer z GHCi, interaktywnym środowiskiem Haskella, które może pełnić funkcję podstawowego debugera. Wystartuj go ze swoim kodem Haskell i zacznij eksplorować. Oto przykład:

```Haskell
main :: IO ()
main = do
    putStrLn "Hej, jak masz na imię?"
    name <- getLine
    putStrLn $ "Witaj, " ++ name ++ "! Zajmijmy się debugowaniem."
    let result = buggyFunction 5
    print result

buggyFunction :: Int -> Int
buggyFunction n = n * 2 -- Udaj, że tutaj jest błąd
```

Aby rozpocząć debugowanie z GHCi:

```bash
$ ghci YourHaskellFile.hs
```

Ustaw breakpoint na `buggyFunction`:

```Haskell
Prelude> :break buggyFunction
```

Uruchom swój program:

```Haskell
Prelude> :main
Hej, jak masz na imię?
```

Twój program zostaje wstrzymany na `buggyFunction`. Teraz możesz inspekcjonować zmienne, przeskakiwać przez kod i oceniać wyrażenia.

## Pogłębiona analiza:
Historycznie, reputacja Haskella za czyste funkcje i silne typowanie prowadziła do przekonania, że narzędzia do debugowania były mniej krytyczne. Rzeczywistość jest inna—złożone programy zawsze korzystają z dobrych narzędzi do debugowania. GHCi dostarcza podstawowych poleceń debugowania. Jednakże, dla bardziej wizualnego doświadczenia lub aplikacji na większą skalę, można zbadać środowiska IDE z zintegrowanymi debuggerami, takie jak Visual Studio Code z rozszerzeniami Haskell lub wtyczka Haskell w IntelliJ.

Alternatywy dla debugera obejmują używanie instrukcji print, znanych jako "printf debugging", lub wykorzystywanie silnego systemu typów Haskella, aby uczynić nieprawidłowe stany niewyrażalnymi. Jednak nic nie zastąpi czasem krokowego przeglądania kodu.

Jeśli chodzi o szczegóły implementacji, debugger Haskella współpracuje z systemem wykonawczym. Może obsługiwać punkty przerwania, wykonanie krokowe i umożliwiać inspekcję zmiennych. Jednak, ponieważ Haskell jest ewaluowany leniwie, rzeczy mogą stać się trochę nietypowe. Debugowanie programu w Haskellu często oznacza obserwowanie, kiedy i jak są wykonywane wyrażenia.

## Zobacz również:
- [Przewodnik użytkownika GHC - Debugger](https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/debugging.html)
- [Wtyczka IntelliJ Haskell](https://plugins.jetbrains.com/plugin/8258-intellij-haskell)
