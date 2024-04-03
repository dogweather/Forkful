---
date: 2024-01-26 04:46:31.247637-07:00
description: "Komplexa tal, best\xE5ende av en reell del och en imagin\xE4r del (vanligtvis\
  \ skrivna som a + bi), m\xF6jligg\xF6r ber\xE4kningar som \xE4r opraktiska eller\
  \ om\xF6jliga med\u2026"
lastmod: '2024-03-13T22:44:37.650142-06:00'
model: gpt-4-0125-preview
summary: "Komplexa tal, best\xE5ende av en reell del och en imagin\xE4r del (vanligtvis\
  \ skrivna som a + bi), m\xF6jligg\xF6r ber\xE4kningar som \xE4r opraktiska eller\
  \ om\xF6jliga med bara reella tal."
title: Att arbeta med komplexa tal
weight: 14
---

## Hur:
Att hantera komplexa tal i TypeScript kräver en dedikerad klass. Låt oss skapa en och arbeta igenom addition och multiplikation.

```TypeScript
class Complex {
    constructor(public re: number, public im: number) {}

    add(other: Complex): Complex {
        return new Complex(this.re + other.re, this.im + other.im);
    }

    multiply(other: Complex): Complex {
        return new Complex(
            this.re * other.re - this.im * other.im,
            this.re * other.im + this.im * other.re
        );
    }

    toString(): string {
        return `${this.re} + ${this.im}i`;
    }
}

let num1 = new Complex(1, 2);
let num2 = new Complex(3, 4);
let sum = num1.add(num2);
let produkt = num1.multiply(num2);

console.log(`Summa: ${sum.toString()}`); // Utdata: Summa: 4 + 6i
console.log(`Produkt: ${produkt.toString()}`); // Utdata: Produkt: -5 + 10i
```

## Fördjupning
Historiskt sett var komplexa tal kontroversiella - till och med benämnda som 'imaginära' för att uttrycka inledande skepsis. Nu är de grundläggande inom modern matematik och vetenskap.

Alternativ till vår enkla klass kan innebära att använda befintliga bibliotek som `math.js` eller `complex.js`, detaljerade med ytterligare funktioner som trigonometriska funktioner, exponentiering och komplex konjugation.

Vår TypeScript-implementation detaljeras till att definiera aritmetiska operationer. Metoden `add` lägger helt enkelt till motsvarande delar. `multiply` tillämpar FOIL-metoden som används i algebra, med påminnelsen om att `i^2 = -1`.

## Se även
För ytterligare läsning och resurser om komplexa tal och deras användning i programmering, kolla in:

- MDN Komplexa Tal Algebra: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt
- `math.js` bibliotek: https://mathjs.org/docs/datatypes/complex_numbers.html
- `complex.js` bibliotek: https://complex-js.github.io/complex.js/
