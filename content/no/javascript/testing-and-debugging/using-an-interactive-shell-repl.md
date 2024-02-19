---
aliases:
- /no/javascript/using-an-interactive-shell-repl/
date: 2024-01-26 04:15:31.491201-07:00
description: "Interaktive skall, eller REPLer (Read-Eval-Print Looper), lar deg kj\xF8\
  re kode p\xE5 sparket, teste funksjoner, algoritmer, eller tukle med ideer. De er\
  \ kodens\u2026"
lastmod: 2024-02-18 23:08:54.310452
model: gpt-4-0125-preview
summary: "Interaktive skall, eller REPLer (Read-Eval-Print Looper), lar deg kj\xF8\
  re kode p\xE5 sparket, teste funksjoner, algoritmer, eller tukle med ideer. De er\
  \ kodens\u2026"
title: Bruke et interaktivt skall (REPL)
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Interaktive skall, eller REPLer (Read-Eval-Print Looper), lar deg kjøre kode på sparket, teste funksjoner, algoritmer, eller tukle med ideer. De er kodens kladdeark, raske og skitne, uten å sette opp et fullt utviklermiljø.

## Hvordan:
Node.js leveres med en REPL som er tilgjengelig via terminalen. Åpne den, og du er klar til å rulle. Her er en smakebit:

```javascript
$ node
> let sum = (a, b) => a + b;
undefined
> sum(5, 10);
15
> .exit
```

Greit, ikke sant? Definer variabler, funksjoner, eller kjør løkker. Når du er ferdig, tar `.exit` deg tilbake til den virkelige verden.

## Dypdykk
REPLer har vært rundt siden 1960-tallet – LISP var pioneren for konseptet. Ideen: gi umiddelbar tilbakemelding til programmereren. Alternativer? Ved siden av Node.js REPL, finnes det nettleserbaserte konsoller som Chrome DevTools, online sandkasser som JSFiddle, eller fullstendige IDEer som VSCode med interaktive lekeplasser.

Under panseret følger REPL-arbeidsflyter typisk: 
1. Les inn inndata
2. Kompiler og eksekver kode
3. Skriv ut utdata
4. Gå tilbake til start

Det er en enkel, men effektiv syklus som har hatt enorm innvirkning på interaktiv koding.

## Se Også
- [Node.js REPL-dokumentasjon](https://nodejs.org/api/repl.html)
- [Mozillas introduksjon til JavaScript-moduler på REPLer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
- [JSFiddle](https://jsfiddle.net/)
