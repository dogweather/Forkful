---
title:                "Arrotondamento dei numeri"
aliases:
- /it/elixir/rounding-numbers/
date:                  2024-01-26T03:44:34.470558-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arrotondamento dei numeri"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/elixir/rounding-numbers.md"
---

{{< edit_this_page >}}

## Cosa e Perché?
Arrotondare i numeri significa aggiustarli a un valore vicino per semplicità o per corrispondere a una certa precisione. È utile per migliorare la leggibilità, ridurre lo spazio di archiviazione o soddisfare esigenze specifiche del dominio, come i calcoli monetari in cui si desidera arrotondare al centesimo più vicino.

## Come fare:
In Elixir, puoi usare `Float.round/2` per arrotondare un numero in virgola mobile. Puoi specificare il numero di cifre decimali che vuoi mantenere. Ecco come funziona:

```elixir
# Arrotondare un numero a nessun decimale
Float.round(3.14159) # => 3.0

# Arrotondare un numero a 2 decimali
Float.round(3.14159, 2) # => 3.14

# Arrotondare un numero a una precisione negativa al 10 più vicino
Float.round(123.456, -1) # => 120.0
```

## Approfondimento
Arrotondare i numeri è un problema classico nell'informatica, tanto che la scelta della strategia di arrotondamento può influenzare i sistemi finanziari, i calcoli scientifici e altro. `Float.round/2` di Elixir predefinisce l'arrotondamento "all'alta metà", simile all'arrotondamento tradizionale insegnato nelle lezioni di matematica.

Se hai bisogno di altri tipi di arrotondamento, Elixir ti permette di creare il tuo. Considera, per esempio, l'arrotondamento "floor" (sempre verso il basso) o l'arrotondamento "ceiling" (sempre verso l'alto). Usaresti `Float.floor/1` o `Float.ceil/1`, rispettivamente.

```elixir
# Arrotondamento floor
Float.floor(3.999) # => 3.0

# Arrotondamento ceiling
Float.ceil(3.001) # => 4.0
```

Queste alternative aiutano ad adattare l'arrotondamento alle esigenze precise della tua applicazione, sia che si tratti di calcoli finanziari, rendering grafico o approssimazione dei dati.

## Vedere anche
Per maggiori informazioni sulle funzioni di arrotondamento e sui numeri in virgola mobile in Elixir:

- Documenti ufficiali di Elixir su `Float`: https://hexdocs.pm/elixir/Float.html
- Standard IEEE per l'aritmetica in virgola mobile (IEEE 754): https://ieeexplore.ieee.org/document/4610935
