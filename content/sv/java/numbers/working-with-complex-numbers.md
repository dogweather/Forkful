---
date: 2024-01-26 04:42:08.732969-07:00
description: "Komplexa tal utvidgar den reella talaxeln genom till\xE4gget av en imagin\xE4\
  r enhet, `i`, d\xE4r `i^2 = -1`. De \xE4r avg\xF6rande inom omr\xE5den som ingenj\xF6\
  rsvetenskap,\u2026"
lastmod: '2024-03-13T22:44:37.781505-06:00'
model: gpt-4-0125-preview
summary: "Komplexa tal utvidgar den reella talaxeln genom till\xE4gget av en imagin\xE4\
  r enhet, `i`, d\xE4r `i^2 = -1`."
title: Att arbeta med komplexa tal
weight: 14
---

## Hur man gör:
Java har inte inbyggt stöd för komplexa tal, men vi kan skapa vår egen klass eller använda ett bibliotek. Här är ett snabbt exempel på hur man skapar en enkel `ComplexNumber`-klass och använder den:

```java
public class ComplexNumber {
    private double real;
    private double imaginary;

    public ComplexNumber(double real, double imaginary) {
        this.real = real;
        this.imaginary = imaginary;
    }

    public ComplexNumber add(ComplexNumber other) {
        return new ComplexNumber(this.real + other.real, this.imaginary + other.imaginary);
    }

    // ToString för att visa komplexa tal i a + bi-form
    @Override
    public String toString() {
        return String.format("%.1f + %.1fi", real, imaginary);
    }

    // Snabbtest
    public static void main(String[] args) {
        ComplexNumber c1 = new ComplexNumber(2, 3);
        ComplexNumber c2 = new ComplexNumber(1, 4);

        System.out.println("Summa: " + c1.add(c2));
    }
}
```

Exempelutdata för huvudmetoden kommer att vara:

```
Summa: 3.0 + 7.0i
```

## Fördjupning
Före högnivåspråk som Java arbetade programmerare direkt med matematikbibliotek i språk som Fortran eller C för att hantera komplexa operationer. Konceptet går tillbaka till 1500-talet, tillskrivet matematiker som Gerolamo Cardano och Rafael Bombelli.

I Java är `java.lang.Math` gå-till för väsentligheter men hoppar över komplexa tal, troligtvis eftersom inte varje programmerare använder dem. Alternativ? Använd bibliotek. Apache Commons Math tillhandahåller en `Complex`-klass packad med metoder för manipulation. Här är varför det är snyggt att rulla sitt eget dock: Lättvikt, skräddarsytt för dina exakta behov, och inget biblioteksöverhäng.

En viktig detalj: se upp för flyttalsprecisionen. Datorer kan inte representera vissa tal exakt, vilket leder till avrundningsfel. När man utför repetitiva komplexa operationer, kan dessa fel ackumuleras!

## Se även
För djupare dykningar och mer komplexa operationer, kolla:

- [Apache Commons Math](https://commons.apache.org/proper/commons-math/)
- [JScience's Complex class](http://jscience.org/)
- Oracles handledningar om [flyttalsaritmetik](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html)
