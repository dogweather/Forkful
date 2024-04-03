---
date: 2024-01-26 03:45:36.345651-07:00
description: "Arrotondare i numeri significa adeguarli a un determinato grado di precisione.\
  \ I programmatori lo fanno per semplificare i numeri per leggibilit\xE0, per\u2026"
lastmod: '2024-03-13T22:44:43.304139-06:00'
model: gpt-4-0125-preview
summary: Arrotondare i numeri significa adeguarli a un determinato grado di precisione.
title: Arrotondamento dei numeri
weight: 13
---

## Come fare:
Java offre molteplici modi per arrotondare i numeri. Ecco una dimostrazione rapida con `Math.round()`, `BigDecimal` e `DecimalFormat`.

```java
public class RoundingDemo {
    public static void main(String[] args) {
        double num = 123.4567;

        // Utilizzando Math.round()
        long roundedNum = Math.round(num);
        System.out.println(roundedNum); // Output: 123

        // Utilizzando BigDecimal per un controllo maggiore
        BigDecimal bd = new BigDecimal(num).setScale(2, RoundingMode.HALF_UP);
        double roundedBigDecimal = bd.doubleValue();
        System.out.println(roundedBigDecimal); // Output: 123.46

        // Utilizzando DecimalFormat
        DecimalFormat df = new DecimalFormat("#.##");
        String formattedNum = df.format(num);
        System.out.println(formattedNum); // Output: 123.46
    }
}
```

## Approfondimento
Storicamente, arrotondare i numeri è stato essenziale per i calcoli analogici ed è continuato nel calcolo digitale per efficienza e accuratezza. Gli errori di arrotondamento, come quelli derivati dall'aritmetica in virgola mobile, dimostrano che questo non è un problema banale - possono accumularsi e compromettere i calcoli in, ad esempio, applicazioni aerospaziali e finanziarie.

Oltre a `Math.round()`, hai a disposizione `BigDecimal`, che ti dà un controllo più fine sulla scala e sulla modalità di arrotondamento, e `DecimalFormat` per quando devi arrotondare i numeri come parte della formattazione dell'output del testo. Alternative all'arrotondamento includono l'approssimazione per difetto, l'approssimazione per eccesso e la troncatura, che sono modi diversi di gestire la precisione e solitamente gestiti da vari metodi di `Math`.

A seconda del tuo caso d'uso, la strategia di arrotondamento può variare. Ad esempio, `BigDecimal` è l'opzione preferita per i calcoli finanziari, dove la precisione è critica. Al contrario, `Math.round()` è un modo veloce per operazioni di uso generico dove sei meno esigente sulla modalità di arrotondamento.

## Vedi anche
- [Documentazione Java Math di Oracle](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html)
- [Standard IEEE per l'aritmetica in virgola mobile (IEEE 754)](https://ieeexplore.ieee.org/document/4610935)
- [Classe DecimalFormat in Java](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html)
