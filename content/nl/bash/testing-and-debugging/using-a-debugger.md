---
title:                "Een debugger gebruiken"
date:                  2024-01-28T22:08:39.681061-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een debugger gebruiken"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/bash/using-a-debugger.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Een debugger in Bash gebruiken betekent het inzetten van tools om te testen en problemen in je scripts te vinden, zoals het vangen van bugs die je code laten crashen of stiekem verkeerd laten werken. Programmeurs doen dit omdat het veel slimmer is om fouten te vangen voordat ze chaos veroorzaken in een live omgeving.

## Hoe:
Bash wordt niet geleverd met een ingebouwde debugger zoals sommige andere talen, maar je kunt ingebouwde commando's gebruiken zoals `set -x` om te traceren wat er gebeurt. Of, voor een upgrade, is er `bashdb`, een echte debugger om stap voor stap door je code te gaan. Hier is een voorproefje:

```Bash
# Gebruik set -x om te debuggen
set -x
echo "Start debugging"
my_var="Hallo, Debugging Wereld!"
echo $my_var
set +x

# Gebruiken van bashdb
# Installeer bashdb met je pakketbeheerder, bijv., apt, yum, brew.
# Debug een script genaamd my_script.sh:
bashdb my_script.sh
```

Uitvoer wanneer gerund met `set -x`:
```Bash
+ echo 'Start debugging'
Start debugging
+ my_var='Hallo, Debugging Wereld!'
+ echo 'Hallo, Debugging Wereld!'
Hallo, Debugging Wereld!
+ set +x
```

## Diepere Duik
Historisch gezien betekende het debuggen van Bash scripts het bezaaien van je code met `echo` statements. Maar toen kwam `set -x`, waarmee we een kijkje kregen in de runtime uitvoering zonder handmatige printouts. En voor degenen die meer controle willen, kwam de `bashdb` debugger naar voren, geïnspireerd door de gdb debugger voor C/C++.

Wat betreft alternatieven, naast de `set` commando's (`-x`, `-v`, `-e`), omvatten andere opties het doorsturen van output naar een bestand voor analyse of het gebruiken van externe tools zoals ShellCheck voor statische analyse.

Implementatie-gewijs is `set -x` eenvoudig; het is een native Bash-optie die commando's en hun argumenten afdrukt terwijl ze worden uitgevoerd. `bashdb`, aan de andere kant, maakt het mogelijk om door code te stappen, breakpoints te zetten en expressies te evalueren - dingen die je een vechtkans geven tegen meer ontwijkende bugs.

## Zie Ook
- Bash Debugger Project: http://bashdb.sourceforge.net/
- "Pro Bash Programming" door Chris Johnson en Jayant Varma voor geavanceerde scripting.
- ShellCheck voor statische analyse: https://www.shellcheck.net/
