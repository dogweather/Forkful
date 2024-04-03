---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:18:22.752057-07:00
description: "Le espressioni regolari (regex) in Ruby sono schemi utilizzati per identificare\
  \ combinazioni di caratteri nelle stringhe, consentendo agli sviluppatori di\u2026"
lastmod: '2024-03-13T22:44:44.039665-06:00'
model: gpt-4-0125-preview
summary: Le espressioni regolari (regex) in Ruby sono schemi utilizzati per identificare
  combinazioni di caratteri nelle stringhe, consentendo agli sviluppatori di cercare,
  trovare corrispondenze e manipolare testi in modo efficiente.
title: Utilizzo delle espressioni regolari
weight: 11
---

## Come fare:


### Corrispondenza di Base
Per confrontare una stringa con un modello semplice, puoi usare il metodo `match`. Di seguito, verifichiamo se la parola "Ruby" esiste in una stringa data.

```ruby
if /Ruby/.match("Ciao, Ruby!")
  puts "Corrispondenza trovata!"
end
# Output: Corrispondenza trovata!
```

### Corrispondenza dei Modelli con Variabili
Puoi interpolare variabili nella tua regex usando la sintassi `#{}`, rendendo i tuoi modelli dinamici.

```ruby
language = "Ruby"
if /#{language}/.match("Programmare in Ruby è divertente.")
  puts "Parlando di Ruby!"
end
# Output: Parlando di Ruby!
```

### Utilizzare le Regex per la Sostituzione
Il metodo `gsub` ti permette di sostituire ogni occorrenza di un modello con una stringa di sostituzione specificata.

```ruby
puts "foobarfoo".gsub(/foo/, "bar")
# Output: barbarbar
```

### Cattura
Le parentesi in una regex sono usate per catturare parti di una corrispondenza. Il metodo `match` restituisce un oggetto `MatchData`, che puoi usare per accedere alle catture.

```ruby
match_data = /(\w+): (\d+)/.match("Età: 30")
puts match_data[1] # Etichetta catturata
puts match_data[2] # Valore catturato
# Output:
# Età
# 30
```

### Utilizzare Librerie di Terze Parti
Sebbene la libreria standard di Ruby sia potente, talvolta potresti aver bisogno di funzionalità più specializzate. Uno gem popolare per lavorare con le regex è `Oniguruma`, che fornisce caratteristiche regex aggiuntive oltre al motore regex integrato in Ruby.

Installalo usando:
```bash
gem install oniguruma
```

Un esempio di utilizzo potrebbe essere il seguente (assumendo che tu abbia eseguito il comando `require 'oniguruma'` dopo averlo installato):

```ruby
# Questo è un esempio più avanzato e potrebbe richiedere una configurazione aggiuntiva
require 'oniguruma'

pattern = Oniguruma::ORegexp.new('(\d+)')
match_data = pattern.match("Il numero è 42.")
puts match_data[1]
# Output: 42
```

Ricorda, per quanto potenti, le espressioni regolari possono diventare complesse e difficili da gestire per modelli più complicati. Punta alla leggibilità e considera metodi alternativi se la tua regex diventa troppo convoluta.
