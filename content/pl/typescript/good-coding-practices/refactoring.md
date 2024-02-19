---
aliases:
- /pl/typescript/refactoring/
date: 2024-01-26 03:36:38.728545-07:00
description: "Refaktoryzacja to proces restrukturyzacji istniej\u0105cego kodu komputerowego\
  \ bez zmiany jego zewn\u0119trznego zachowania. Programi\u015Bci wykonuj\u0105 j\u0105\
  , aby kod by\u0142\u2026"
lastmod: 2024-02-18 23:08:49.356139
model: gpt-4-0125-preview
summary: "Refaktoryzacja to proces restrukturyzacji istniej\u0105cego kodu komputerowego\
  \ bez zmiany jego zewn\u0119trznego zachowania. Programi\u015Bci wykonuj\u0105 j\u0105\
  , aby kod by\u0142\u2026"
title: Refaktoryzacja
---

{{< edit_this_page >}}

## Co i dlaczego?
Refaktoryzacja to proces restrukturyzacji istniejącego kodu komputerowego bez zmiany jego zewnętrznego zachowania. Programiści wykonują ją, aby kod był czystszy, łatwiejszy do utrzymania i aby zredukować jego złożoność, co ułatwia zrozumienie kodu osobie, która zaczyna się z nim zapoznawać.

## Jak to zrobić:
Rozważmy funkcję TypeScript, która miała lepsze dni - jest nieco bałaganu i potrzebuje trochę troskliwej opieki:

```typescript
function userInfo(data: any): string {
    return "User Info: " + data.name + ", " + data.age + ", " + data.email + ";" ;
}
```
Po refaktoryzacji może to wyglądać tak:

```typescript
interface User {
    name: string;
    age: number;
    email: string;
}

function formatUserInfo(user: User): string {
    return `User Info: ${user.name}, ${user.age}, ${user.email};`;
}
```

Drugi przykład jest bardziej solidny, wykorzystuje system typów TypeScript za pomocą `interface`, aby uniknąć potencjalnych błędów wykonania i poprawić czytelność.

## Szczegółowe omówienie
Refaktoryzacja nie jest nowoczesnym pojęciem; ewoluowała razem z programowaniem, stając się bardziej sformalizowana po wydaniu książki Martina Fowlera "Refaktoryzacja: Ulepszanie struktury istniejącego kodu" w 1999 roku. Jest kluczowa w środowisku rozwoju Agile, ułatwiając adaptacyjne zmiany kodu. Niektóre alternatywy dla ręcznej refaktoryzacji to narzędzia automatyczne, takie jak TSLint czy własny serwer językowy TypeScript, które mogą sugerować, a nawet wykonywać niektóre zadania refaktoryzacyjne za Ciebie. Szczegóły implementacji zwykle obejmują rozpoznawanie "zapachów kodu", takich jak zduplikowany kod, długie metody czy duże klasy, oraz stosowanie wzorców w celu ich naprawienia — takich jak ekstrakcja metod, przenoszenie do bardziej odpowiednich klas lub używanie prostszych konstrukcji. Te wzorce są kluczowe do zrozumienia jak i dlaczego dokonuje się refaktoryzacji.

## Zobacz również
- [Książka "Refaktoryzacja: Ulepszanie struktury istniejącego kodu" autorstwa Martina Fowlera](https://martinfowler.com/books/refactoring.html)
- [TSLint do statycznej analizy kodu](https://palantir.github.io/tslint/)
- [Rozumienie zapachów kodu](https://refactoring.guru/refactoring/smells)
