---
date: 2024-01-26 04:15:42.127682-07:00
description: "Interaktywne pow\u0142oki, czyli REPL-y (Read-Eval-Print Loops - P\u0119\
  tle Czytaj-Wykonaj-Wypisz), pozwalaj\u0105 na bie\u017C\u0105co uruchamia\u0107\
  \ kod, testowa\u0107 funkcje, algorytmy\u2026"
lastmod: '2024-03-13T22:44:35.798136-06:00'
model: gpt-4-0125-preview
summary: "Interaktywne pow\u0142oki, czyli REPL-y (Read-Eval-Print Loops - P\u0119\
  tle Czytaj-Wykonaj-Wypisz), pozwalaj\u0105 na bie\u017C\u0105co uruchamia\u0107\
  \ kod, testowa\u0107 funkcje, algorytmy lub bawi\u0107 si\u0119 pomys\u0142ami."
title: Korzystanie z interaktywnego shella (REPL)
weight: 34
---

## Jak to zrobić:
Node.js jest dostarczany z REPL dostępnym poprzez terminal. Otwórz go, a będziesz gotowy do działania. Oto mała próbka:

```javascript
$ node
> let sum = (a, b) => a + b;
undefined
> sum(5, 10);
15
> .exit
```

Proste, prawda? Definiuj zmienne, funkcje lub uruchamiaj pętle. Kiedy skończysz, `.exit` zabierze cię z powrotem do rzeczywistości.

## Dogłębna analiza
REPL-e istnieją od lat 60. XX wieku – LISP zapoczątkował ten koncept. Ideą było zapewnienie natychmiastowego feedbacku dla programisty. Alternatywy? Poza REPL Node.js, są też konsolowe narzędzia przeglądarki takie jak Chrome DevTools, online piaskownice takie jak JSFiddle, czy pełne IDE takie jak VSCode z interaktywnymi placami zabaw.

Pod kapotem, przepływ pracy REPL zazwyczaj obejmuje: 
1. Odczyt wejścia
2. Kompilację i wykonanie kodu
3. Wypisanie wyniku
4. Powrót do początku

To prosta, aczkolwiek skuteczna pętla, która miała ogromny wpływ na interaktywne programowanie.

## Zobacz także
- [Dokumentacja REPL Node.js](https://nodejs.org/api/repl.html)
- [Wprowadzenie do modułów JavaScript na REPL-ach od Mozilli](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
- [JSFiddle](https://jsfiddle.net/)
