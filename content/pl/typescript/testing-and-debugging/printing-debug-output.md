---
date: 2024-01-20 17:53:28.788973-07:00
description: "Wypisywanie informacji debuguj\u0105cych to wy\u015Bwietlanie danych,\
  \ kt\xF3re pomagaj\u0105 programi\u015Bcie zrozumie\u0107, co si\u0119 dzieje w\
  \ kodzie. Programi\u015Bci robi\u0105 to, by szybko\u2026"
lastmod: '2024-03-13T22:44:35.141461-06:00'
model: gpt-4-1106-preview
summary: "Wypisywanie informacji debuguj\u0105cych to wy\u015Bwietlanie danych, kt\xF3\
  re pomagaj\u0105 programi\u015Bcie zrozumie\u0107, co si\u0119 dzieje w kodzie."
title: "Drukowanie komunikat\xF3w debugowania"
weight: 33
---

## How to: (Jak to zrobić?)
W TypeScript możesz wykorzystać `console.log` do pokazywania debug info. Spójrz jak to działa:

```TypeScript
function addNumbers(a: number, b: number): number {
    console.log(`Adding ${a} + ${b}`);
    return a + b;
}

const sum = addNumbers(2, 3);
console.log(`Sum: ${sum}`);
```

Output będzie wyglądać tak:
```
Adding 2 + 3
Sum: 5
```

Możesz też użyć `console.error` dla błędów i `console.warn` dla ostrzeżeń.

```TypeScript
function subtractNumbers(a: number, b: number): number {
    if (b > a) {
        console.warn('Subtracting larger number from smaller number.');
    }
    return a - b;
}

const result = subtractNumbers(5, 10);
console.error(`Result: ${result}`);
```

W ten sposób otrzymujemy:
```
Warning: Subtracting larger number from smaller number.
Error: Result: -5
```

## Deep Dive (Dogłębna analiza)
Debugowanie kodu przez wypisywanie ma swoje korzenie w początkach informatyki, gdzie logi były sprawdzane na papierze. Dziś mamy wiele narzędzi, ale `console.log` wciąż jest używany przez swe prostotę i uniwersalność.

Alternatywy dla `console.log` w TypeScript/JavaScript to: debugger oraz zaawansowane systemy logowania jak Winston czy Bunyan, które oferują filtrowanie i lepsze zarządzanie logami.

Szczegółowo, `console` w Node.js i przeglądarkach może mieć różne implementacje, choć API jest standardowe. Dlatego czasami logi mogą różnić się między środowiskami.

## See Also (Zobacz również)
- MDN Web Docs na temat `Console`: https://developer.mozilla.org/en-US/docs/Web/API/Console
- Node.js dokumentacje dla `console`: https://nodejs.org/api/console.html
- Porównanie bibliotek do logowania: https://stackify.com/best-javascript-logging-libraries/
