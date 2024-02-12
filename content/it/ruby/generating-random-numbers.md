---
title:                "Generazione di numeri casuali"
aliases:
- it/ruby/generating-random-numbers.md
date:                  2024-01-27T20:34:50.133702-07:00
model:                 gpt-4-0125-preview
simple_title:         "Generazione di numeri casuali"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/ruby/generating-random-numbers.md"
---

{{< edit_this_page >}}

## Cosa & Perché?

Generare numeri casuali in Ruby comporta la creazione di numeri che non possono essere previsti logicamente, fondamentale per scenari come le simulazioni, la crittografia e i giochi. I programmatori utilizzano la casualità per aggiungere imprevedibilità o imitare le variabilità della vita reale nelle loro applicazioni.

## Come fare:

Ruby fornisce diversi metodi per generare numeri casuali, principalmente tramite la classe `Random`.

### Numero Casuale di Base

Per generare un numero casuale di base:

```Ruby
puts rand(10) # Genera un numero casuale tra 0 e 9
```

### Numero Casuale Entro un Intervallo

Per un numero casuale all'interno di uno specifico intervallo:

```Ruby
puts rand(1..10) # Genera un numero casuale tra 1 e 10
```

### Utilizzando la Classe Random

Per creare una sequenza ripetibile di numeri casuali, puoi usare la classe `Random` con un seme.

```Ruby
random_generator = Random.new(1234)
puts random_generator.rand(100) # Genera un numero "casuale" prevedibile
```

### Generare un Elemento Casuale di un Array

Selezionare un elemento casuale da un array:

```Ruby
colors = ["red", "blue", "green", "yellow"]
puts colors.sample # Seleziona casualmente un elemento dall'array
```

### Esempio di Output:

Ogni frammento di codice sopra, se eseguito, produrrà output differenti a causa della loro natura casuale. Per esempio, `rand(10)` potrebbe dare in output `7`, mentre `colors.sample` potrebbe dare in output `"green"`.

## Approfondimento

Il concetto di generazione di numeri casuali in informatica è paradossale perché i computer seguono istruzioni deterministiche. I metodi iniziali dipendevano fortemente dall'input esterno per raggiungere l'imprevedibilità. La casualità di Ruby si basa sull'algoritmo Mersenne Twister, un generatore di numeri pseudo-casuali noto per il suo vasto periodo e distribuzione uniforme, rendendolo altamente adatto per applicazioni che richiedono casualità di alta qualità.

Sebbene i metodi integrati in Ruby soddisfino bene la maggior parte delle necessità, potrebbero non essere sufficienti per tutti gli scopi crittografici, poiché la prevedibilità dei numeri pseudo-casuali può essere una vulnerabilità. Per la sicurezza crittografica, gli sviluppatori Ruby potrebbero esplorare librerie come `OpenSSL::Random`, che sono progettate per produrre numeri casuali criptograficamente sicuri, garantendo un'alta imprevedibilità per applicazioni sensibili.
