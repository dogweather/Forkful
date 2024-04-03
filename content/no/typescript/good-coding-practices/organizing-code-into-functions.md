---
date: 2024-01-26 01:16:22.474002-07:00
description: "\xC5 organisere kode i funksjoner betyr \xE5 bryte opp koden din i gjenbrukbare,\
  \ modul\xE6re blokker. Vi gj\xF8r dette for \xE5 holde ting DRY (Don't Repeat Yourself),\u2026"
lastmod: '2024-03-13T22:44:40.537827-06:00'
model: gpt-4-0125-preview
summary: "\xC5 organisere kode i funksjoner betyr \xE5 bryte opp koden din i gjenbrukbare,\
  \ modul\xE6re blokker."
title: Organisering av kode i funksjoner
weight: 18
---

## Hvordan:
Forestille deg at du lager en grunnleggende kalkulator. I stedet for å skrive tilleggslogikken overalt hvor du trenger den, opprett en `add`-funksjon:

```TypeScript
function add(x: number, y: number): number {
  return x + y;
}

console.log(add(5, 7)); // Eksempel på utskrift: 12
```

Nå, la oss si at vi trenger en funksjon for å multiplisere:

```TypeScript
function multiply(x: number, y: number): number {
  return x * y;
}

console.log(multiply(3, 4)); // Eksempel på utskrift: 12
```
Legger du merke til hvordan vi fokuserer på én oppgave per funksjon? Det er kjernen i organisering av kode.

## Dypdykk
Historisk sett, ettersom programmeringsspråk har utviklet seg, ble funksjoner avgjørende for å strukturere kode, hentet fra matematiske funksjoner. De er en stift i prosedyreprogrammering og lever videre i paradigmer for objektorientert programmering og funksjonell programmering.

Alternativer? Du kunne bare unngå å bruke funksjoner, men det er en billett til Spaghetti Town. Eller du kunne gå for OOP (Objektorientert Programmering) og pakke funksjonalitet inn i metoder - som i hovedsak er funksjoner som tilhører objekter.

Når det gjelder implementering, insisterer TypeScript på typer. Å definere inngangs- og utgangstyper for funksjoner er ikke bare god skikk; det er et must for ren TypeScript-kode. Pluss, med TypeScript, får du smarte funksjoner som overbelastninger, generika og valgfrie parametere for å superlade funksjonene dine.

## Se også
Sjekk ut disse ressursene for å oppgradere ditt funksjonsspill:

- [TypeScript Handbook – Functions](https://www.typescriptlang.org/docs/handbook/2/functions.html): Din Bibel for TypeScript-funksjoner.
- [Clean Code JavaScript](https://github.com/ryanmcdermott/clean-code-javascript#functions): Bruk Clean Code-prinsipper på JavaScript-funksjonene dine.
- [You Don’t Know JS – Scope & Closures](https://github.com/getify/You-Dont-Know-JS): Få et grep om hvordan funksjoner fungerer med scope og closures i JavaScript.
