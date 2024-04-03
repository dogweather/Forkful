---
date: 2024-01-26 01:11:58.382150-07:00
description: "Att organisera kod i funktioner handlar om att bryta upp ditt program\
  \ i \xE5teranv\xE4ndbara, modul\xE4ra delar som identifieras med ett namn. Vi g\xF6\
  r det f\xF6r att\u2026"
lastmod: '2024-03-13T22:44:37.704031-06:00'
model: gpt-4-1106-preview
summary: "Att organisera kod i funktioner handlar om att bryta upp ditt program i\
  \ \xE5teranv\xE4ndbara, modul\xE4ra delar som identifieras med ett namn."
title: Att organisera kod i funktioner
weight: 18
---

## Hur man gör:
Anta att du har kod som beräknar en cirkels area flera gånger. Istället för att upprepa formeln, så omsluter du den med en funktion.

```Rust
fn berakna_cirkel_area(radius: f64) -> f64 {
    std::f64::consts::PI * radius.powi(2)
}

fn main() {
    let radius = 5.0;
    let area = berakna_cirkel_area(radius);
    println!("Arean av cirkeln är: {}", area);
}
```

Utmatning:

```
Arean av cirkeln är: 78.53981633974483
```

## Fördjupning
Historiskt sett kommer funktioner från matematiken, där de mappar indata till utdata. Inom programmering har de funnits sedan monteringsdagarna, fast då kallade vi dem 'subrutiner'. Rusts funktioner kan returnera värden och till och med andra funktioner tack vare förstaklassfunktioner och stängningar.

Alternativ? Inline-kod eller makron, men de är röriga för komplex logik. Objekt med metoder är ett annat sätt att organisera funktionalitet, en annan smak än fristående funktioner.

Implementeringen i Rust är ganska rakt på sak. Funktioner deklarerar sina parametertyper och returtyp. De namnges 'ormcase' enligt konvention. Du har dina offentliga funktioner (`pub fn`) för användning utanför modulen och privata för intern användning. Och Rust har denna coola funktion där du inte behöver ett `return`-nyckelord för det sista uttrycket i en funktion.

## Se även
Kolla in dessa för mer information:
- The Rust Programming Language Book: [Functions](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html)
- Rust by Example on [Functions](https://doc.rust-lang.org/rust-by-example/fn.html)
