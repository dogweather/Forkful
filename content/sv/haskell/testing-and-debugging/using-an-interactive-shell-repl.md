---
aliases:
- /sv/haskell/using-an-interactive-shell-repl/
date: 2024-01-26 04:14:55.960533-07:00
description: "En interaktiv skal, eller REPL (Read-Eval-Print Loop), i Haskell l\xE5\
  ter dig k\xF6ra kodsnuttar live. Det \xE4r en lekplats f\xF6r snabb feedback, testning\
  \ av\u2026"
lastmod: 2024-02-18 23:08:51.838677
model: gpt-4-0125-preview
summary: "En interaktiv skal, eller REPL (Read-Eval-Print Loop), i Haskell l\xE5ter\
  \ dig k\xF6ra kodsnuttar live. Det \xE4r en lekplats f\xF6r snabb feedback, testning\
  \ av\u2026"
title: "Anv\xE4nda en interaktiv skal (REPL)"
---

{{< edit_this_page >}}

## Vad & Varför?
En interaktiv skal, eller REPL (Read-Eval-Print Loop), i Haskell låter dig köra kodsnuttar live. Det är en lekplats för snabb feedback, testning av funktioner och inlärning av språket.

## Hur:
För att starta GHCi (Glasgow Haskell Compiler's interaktiva miljö), skriv helt enkelt `ghci` i din terminal. Så här använder du det:

```Haskell
Prelude> låt x = 5
Prelude> x * 2
10
Prelude> :t x
x :: Num a => a
```

Exempelutmatningen förklarar att `x` är en numerisk variabel och visar att fördubbling av den resulterar i 10.

## Djupdykning:
Haskells GHCi har kommit långt sedan sin början. Det erbjuder en rik uppsättning funktioner som flikkomplettering, flerledsinmatning och paketladdning. Alternativ som Hugs är mestadels historiska nu, med GHCi som standard. GHCi kompilerar kod i realtid varje gång du matar in ett uttryck, vilket ger dig ett effektivt sätt att testa din Haskell-kod.

## Se även:
- [Användarguiden för GHC – GHCi](https://downloads.haskell.org/ghc/latest/docs/html/users_guide/ghci.html)
- [Lär dig Haskell för stor nytta! – Att börja](http://learnyouahaskell.com/starting-out#hello-world)
- [Haskell Wiki – GHC/GHCi](https://wiki.haskell.org/GHC/GHCi)
