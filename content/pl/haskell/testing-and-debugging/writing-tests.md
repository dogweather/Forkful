---
aliases:
- /pl/haskell/writing-tests/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:30:48.293256-07:00
description: "Pisanie test\xF3w w Haskellu polega na zapewnieniu, \u017Ce twoje funkcje\
  \ dzia\u0142aj\u0105 zgodnie z oczekiwaniami poprzez automatyczne kontrole. Programi\u015B\
  ci robi\u0105 to,\u2026"
lastmod: 2024-02-18 23:08:49.656837
model: gpt-4-0125-preview
summary: "Pisanie test\xF3w w Haskellu polega na zapewnieniu, \u017Ce twoje funkcje\
  \ dzia\u0142aj\u0105 zgodnie z oczekiwaniami poprzez automatyczne kontrole. Programi\u015B\
  ci robi\u0105 to,\u2026"
title: "Pisanie test\xF3w"
---

{{< edit_this_page >}}

## Co & Dlaczego?

Pisanie testów w Haskellu polega na zapewnieniu, że twoje funkcje działają zgodnie z oczekiwaniami poprzez automatyczne kontrole. Programiści robią to, aby wczesne wykrywać błędy, ułatwiać refaktoryzację i dokumentować zachowanie, co czyni bazę kodu bardziej utrzymywalną i skalowalną.

## Jak to zrobić:

Haskell obsługuje różne frameworki do testowania, ale dwa popularne to `Hspec` i `QuickCheck`. Hspec pozwala definiować ludzko czytelne specyfikacje dla twojego kodu, podczas gdy QuickCheck pozwala automatycznie generować testy, opisując właściwości, które twój kod powinien spełniać.

### Korzystanie z Hspec

Najpierw dodaj `hspec` do konfiguracji narzędzia budującego (np. `stack.yaml` lub plik `cabal`). Następnie zaimportuj `Test.Hspec` i napisz testy jako specyfikacje:

```haskell
-- file: spec/MyLibSpec.hs
import Test.Hspec
import MyLib (add)

main :: IO ()
main = hspec $ describe "MyLib.add" $ do
  it "dodaje dwie liczby" $
    add 1 2 `shouldBe` 3

  it "zwraca pierwszą liczbę przy dodawaniu zera" $
    add 5 0 `shouldBe` 5
```

Następnie uruchom swoje testy za pomocą narzędzia budującego, co może dać taki wynik:

```
MyLib.add
  - dodaje dwie liczby
  - zwraca pierwszą liczbę przy dodawaniu zera

Zakończono w 0.0001 sekundy
2 przykłady, 0 porażek
```

### Korzystanie z QuickCheck

Z QuickCheck wyrażasz właściwości, które twoje funkcje powinny spełniać. Dodaj `QuickCheck` do konfiguracji projektu, a następnie zaimportuj go:

```haskell
-- file: test/MyLibProperties.hs
import Test.QuickCheck
import MyLib (add)

prop_addAssociative :: Int -> Int -> Int -> Bool
prop_addAssociative x y z = x + (y + z) == (x + y) + z

prop_addCommutative :: Int -> Int -> Bool
prop_addCommutative x y = x + y == y + x

main :: IO ()
main = do
  quickCheck prop_addAssociative
  quickCheck prop_addCommutative
```

Uruchomienie tych testów będzie automatycznie generowało dane wejściowe do sprawdzenia określonych właściwości:

```
+++ OK, przeszło 100 testów.
+++ OK, przeszło 100 testów.
```

W przykładach zarówno z Hspec, jak i QuickCheck, zestawy testów służą jako wykonywalna dokumentacja, która może automatycznie weryfikować poprawność Twojego kodu.
