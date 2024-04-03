---
date: 2024-01-20 17:39:13.877799-07:00
description: "Convertire una stringa in minuscolo significa cambiare tutti i caratteri\
  \ dalla forma maiuscola alla forma minuscola. I programmatori lo fanno per\u2026"
lastmod: '2024-03-13T22:44:44.036832-06:00'
model: gpt-4-1106-preview
summary: Convertire una stringa in minuscolo significa cambiare tutti i caratteri
  dalla forma maiuscola alla forma minuscola.
title: Conversione di una stringa in minuscolo
weight: 4
---

## How to: (Come fare:)
```Ruby
# Esempio base di conversione in minuscolo
s1 = "Ciao Mondo!"
s1_downcase = s1.downcase
puts s1_downcase # => "ciao mondo!"

# Uso con caratteri accentati e speciali
s2 = "È un Bellissimo Giorno!"
s2_downcase = s2.downcase
puts s2_downcase # => "è un bellissimo giorno!"
```
Questi esempi mostrano il metod `downcase` applicato a delle stringhe in Ruby.

## Deep Dive (Analisi Approfondita)
Nel Ruby, il metodo `downcase` è incluso fin dalle prime versioni. Esso fa parte della classe `String` e prende ogni lettera maiuscola e la trasforma nella corrispondente minuscola. Tuttavia, prima di Ruby 2.4, `downcase` aveva dei limiti con lettere con accenti o other caratteri non-ASCII. Questi hanno ottenuto un miglior supporto con l'introduzione di `downcase(:fold)`.

Alternative al metodo `downcase` includono `downcase!`, che modifica la stringa originale in-place, e `casecmp`, per fare confronti tra stringhe che ignorano la capitalizzazione senza cambiare le stringhe. 

A livello di implementazione, `downcase` fa parte delle operazioni di encoding-aware, significando che può gestire correttamente stringhe in diverse codifiche, a patto che la codifica della stringa comprenda la mappatura a caso.

## See Also (Vedi Anche)
- La documentazione ufficiale di Ruby sull'uso del metodo `String#downcase`: [Ruby Doc downcase](https://ruby-doc.org/core-2.7.0/String.html#method-i-downcase)
- Comparazioni indipendenti dalla capitalizzazione: [Ruby Doc casecmp](https://ruby-doc.org/core-2.7.0/String.html#method-i-casecmp)
- Informazioni sull'unicode e il case mapping: [Unicode Case Mapping](http://unicode.org/faq/casemap_charprop.html)
