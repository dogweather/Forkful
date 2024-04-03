---
date: 2024-01-26 03:47:06.179476-07:00
description: "Arrotondare i numeri significa tagliare un numero a una precisione specifica.\
  \ I programmatori lo fanno per controllare l'output numerico per leggibilit\xE0\
  ,\u2026"
lastmod: '2024-03-13T22:44:43.171165-06:00'
model: gpt-4-0125-preview
summary: Arrotondare i numeri significa tagliare un numero a una precisione specifica.
title: Arrotondamento dei numeri
weight: 13
---

## Come fare:
In TypeScript, l'arrotondamento può essere eseguito utilizzando diversi metodi. Ecco una rapida panoramica:

```typescript
// Math.round arrotonda all'intero più vicino
console.log(Math.round(1.5)); // Output: 2

// Math.ceil arrotonda all'intero superiore più vicino
console.log(Math.ceil(1.1)); // Output: 2

// Math.floor arrotonda all'intero inferiore più vicino
console.log(Math.floor(1.8)); // Output: 1

// toFixed arrotonda a un numero fisso di decimali
let num = 1.23456;
console.log(num.toFixed(2)); // Output: "1.23"
// Nota: toFixed restituisce una stringa! Usa parseFloat per convertire di nuovo se necessario.
console.log(parseFloat(num.toFixed(2))); // Output: 1.23
```

## Approfondimento
Nel passato, l'arrotondamento era necessario a causa dello spazio limitato e dei problemi di precisione nei primi computer. Oggi, l'aritmetica in virgola mobile può portare a risultati bizzarri a causa di come i numeri sono memorizzati in binario. Le alternative all'arrotondamento includono floor, ceil, e trunc (per tagliare i decimali senza arrotondare).

Gli interni meritano una nota: `Math.round` segue la regola del "round half up" (noto anche come "arrotondamento commerciale"), mentre `Math.floor` e `Math.ceil` sono semplici. `toFixed` può causare risultati inaspettati perché restituisce una stringa, e arrotonda utilizzando il "round half to even" (noto anche come "arrotondamento bancario"), particolarmente utile per ridurre il bias nell'arrotondare più volte gli stessi numeri.

## Vedi Anche
- [MDN - Math.round()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round)
- [MDN - Math.ceil()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil)
- [MDN - Math.floor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
- [MDN - toFixed()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
- [Standard IEEE per l'Aritmetica in Virgola Mobile (IEEE 754)](https://ieeexplore.ieee.org/document/4610935)
