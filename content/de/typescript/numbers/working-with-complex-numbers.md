---
date: 2024-01-26 04:46:08.755653-07:00
description: "Komplexe Zahlen, bestehend aus einem Realteil und einem Imagin\xE4rteil\
  \ (\xFCblicherweise geschrieben als a + bi), erm\xF6glichen Berechnungen, die mit\
  \ nur reellen\u2026"
lastmod: '2024-03-13T22:44:53.625485-06:00'
model: gpt-4-0125-preview
summary: "Komplexe Zahlen, bestehend aus einem Realteil und einem Imagin\xE4rteil\
  \ (\xFCblicherweise geschrieben als a + bi), erm\xF6glichen Berechnungen, die mit\
  \ nur reellen Zahlen praktisch unm\xF6glich oder nicht durchf\xFChrbar w\xE4ren."
title: Umgang mit komplexen Zahlen
weight: 14
---

## Wie:
Die Handhabung komplexer Zahlen in TypeScript erfordert eine dedizierte Klasse. Lassen Sie uns eine erstellen und uns mit Addition und Multiplikation auseinandersetzen.

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
let product = num1.multiply(num2);

console.log(`Summe: ${sum.toString()}`); // Ausgabe: Summe: 4 + 6i
console.log(`Produkt: ${product.toString()}`); // Ausgabe: Produkt: -5 + 10i
```

## Vertiefung
Historisch gesehen waren komplexe Zahlen umstritten - sogar als 'imaginär' geprägt, um die anfängliche Skepsis auszudrücken. Jetzt sind sie grundlegend in der modernen Mathematik und Wissenschaft.

Alternativen zu unserer einfachen Klasse könnten die Verwendung bestehender Bibliotheken wie `math.js` oder `complex.js` einschließen, die mit zusätzlichen Funktionen wie trigonometrischen Funktionen, Exponentiation und Komplexkonjugation ausgestattet sind.

Die Details unserer TypeScript-Implementierung kommen auf die Definition von arithmetischen Operationen herunter. Die Methode `add` addiert einfach die entsprechenden Teile. `multiply` wendet die FOIL-Methode an, die in der Algebra verwendet wird, wobei man sich daran erinnert, dass `i^2 = -1` ist.

## Siehe auch
Für weiterführende Literatur und Ressourcen zu komplexen Zahlen und ihrer Verwendung in der Programmierung, siehe:

- MDN Komplexe Zahl Algebra: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt
- `math.js` Bibliothek: https://mathjs.org/docs/datatypes/complex_numbers.html
- `complex.js` Bibliothek: https://complex-js.github.io/complex.js/
