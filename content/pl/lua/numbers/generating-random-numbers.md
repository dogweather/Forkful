---
date: 2024-01-27 20:34:58.903709-07:00
description: "Generowanie losowych liczb w programowaniu dotyczy wytwarzania nieprzewidywalnych\
  \ warto\u015Bci liczbowych, kt\xF3re mog\u0105 by\u0107 wykorzystywane do r\xF3\u017C\
  nych cel\xF3w,\u2026"
lastmod: '2024-03-13T22:44:35.535863-06:00'
model: gpt-4-0125-preview
summary: "Generowanie losowych liczb w programowaniu dotyczy wytwarzania nieprzewidywalnych\
  \ warto\u015Bci liczbowych, kt\xF3re mog\u0105 by\u0107 wykorzystywane do r\xF3\u017C\
  nych cel\xF3w, takich jak symulacje, gry czy aplikacje bezpiecze\u0144stwa."
title: Generowanie liczb losowych
weight: 12
---

## Jak to zrobić:
Lua oferuje wbudowane wsparcie dla generowania liczb losowych za pomocą funkcji `math.random`. Funkcja ta może być używana na wiele sposobów, w zależności od pożądanego wyniku:

1. **Generowanie losowej liczby zmiennoprzecinkowej między 0 a 1:**

```Lua
print(math.random())
```

Przykładowy wynik może być `0.13117647051304`. Każde uruchomienie produkuje inną wartość.

2. **Generowanie losowej liczby całkowitej w określonym zakresie:**

Aby wyprodukować losową liczbę całkowitą między dwoma granicami, włącznie, najpierw musisz ustawić ziarno używając `math.randomseed(os.time())` dla zmienności, następnie wywołać `math.random` z dwoma argumentami:

```Lua
math.randomseed(os.time())
print(math.random(1, 10)) -- Generuje losową liczbę całkowitą między 1 a 10
```

Przykładowy wynik może być `7`. Znowu, wynik będzie się różnić przy każdym wykonaniu.

Ustawienie ziarna za pomocą `math.randomseed` jest kluczowe, ponieważ bez tego `math.random` mogłoby generować tę samą sekwencję liczb za każdym razem, gdy program jest uruchamiany. Zazwyczaj, ziarnowanie przy użyciu bieżącego czasu, `os.time()`, zapewnia różne sekwencje przy każdym wykonaniu.

## Szczegółowe omówienie
Mechanizm leżący u podstaw generowania liczb losowych w Lua (i większości języków programowania) nie jest naprawdę losowy, ale pseudolosowy, generowany przez algorytm. Te pseudolosowe generatory liczb (PRNGs) są deterministyczne i wymagają ziarna do rozpoczęcia sekwencji generowania liczby. Wybór ziarnowania jest kluczowy dla jakości losowości, dlatego stosowanie bieżącego czasu jest powszechną praktyką.

Historycznie, możliwości generowania liczb losowych w Lua ewoluowały. Wcześniejsze wersje polegały na funkcji `rand()` biblioteki standardowej C, która różniła się jakością i wydajnością w zależności od implementacji. Obecna wersja Lua poprawia to, możliwie używając bardziej solidnych mechanizmów w zależności od leżącej u podstaw platformy, oferując większą spójność i użyteczność w generowaniu liczb losowych.

Dla projektów wymagających kryptograficznej losowości, wbudowana funkcjonalność Lua może nie wystarczyć z powodu deterministycznego charakteru PRNGs. W takich przypadkach, programiści często zwracają się ku zewnętrznym bibliotekom lub specyficznym dla systemu API, które mogą dostarczać nieterministyczne liczby losowe odpowiednie dla aplikacji wysokiego bezpieczeństwa.
