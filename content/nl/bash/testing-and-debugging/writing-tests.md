---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:12:45.097598-07:00
description: "Het schrijven van tests verifieert dat code zich gedraagt zoals verwacht.\
  \ Programmeurs testen om bugs vroegtijdig te ontdekken, betrouwbaarheid te\u2026"
lastmod: '2024-03-13T22:44:50.986174-06:00'
model: gpt-4-0125-preview
summary: Het schrijven van tests verifieert dat code zich gedraagt zoals verwacht.
title: Tests Schrijven
weight: 36
---

## Hoe:
Bash heeft geen ingebouwd testframework, maar je kunt eenvoudige testcommando's en beweringen gebruiken. Laten we een functie schrijven en deze testen met `test` of `[ ]`.

Bash-functie om te testen:
```Bash
is_number() {
  [[ $1 =~ ^[0-9]+$ ]] && return 0 || return 1
}
```

Testgeval:
```Bash
test_is_number() {
  is_number 42 && echo "Pass: 42 is een nummer" || echo "Fail: 42 is geen nummer"
  is_number abc && echo "Pass: abc is een nummer" || echo "Fail: abc is geen nummer"
}

test_is_number
```

Voorbeelduitvoer:
```
Pass: 42 is een nummer
Fail: abc is geen nummer
```

## Diepgaande duik
Bash-testen is geëvolueerd. Aanvankelijk zou men handmatig scriptuitvoer controleren. Toen kwam het `test` commando in de jaren 70, waardoor scripts zelf voorwaarden konden controleren. Alternatieven zoals `Bats`, een daadwerkelijk Bash-testframework, bieden meer functies maar vereisen een externe installatie. Het combineren van `Bats` met Continuous Integration (CI) tools zoals Jenkins of GitHub Actions leidt tot robuustere testpijplijnen. Terwijl je implementeert, onthoud dat Bash minder gedetailleerd is dan de testframeworks van andere talen; gebruik `-eq` voor het vergelijken van getallen, `-z` om te controleren of een string leeg is, en `[[ ]]` voor geavanceerde functies zoals patroonmatching.

## Zie ook
- [Bats: Bash Automated Testing System](https://github.com/bats-core/bats-core)
- [Geavanceerde Bash-scriptinghandleiding: Testen en vertakken](https://tldp.org/LDP/abs/html/testbranch.html)
- [ShellCheck: Een statische analysetool voor shellscripts](https://www.shellcheck.net/)
