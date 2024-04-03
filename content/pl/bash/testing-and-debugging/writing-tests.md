---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:29:36.706359-07:00
description: "Pisanie test\xF3w w Bashu obejmuje tworzenie skrypt\xF3w testowych w\
  \ celu weryfikacji funkcjonalno\u015Bci twoich skrypt\xF3w Bash. Programi\u015B\
  ci przeprowadzaj\u0105 testy,\u2026"
lastmod: '2024-03-13T22:44:35.588560-06:00'
model: gpt-4-0125-preview
summary: "Pisanie test\xF3w w Bashu obejmuje tworzenie skrypt\xF3w testowych w celu\
  \ weryfikacji funkcjonalno\u015Bci twoich skrypt\xF3w Bash."
title: "Pisanie test\xF3w"
weight: 36
---

## Jak to zrobić:
Bash nie posiada wbudowanego frameworka do testowania, ale można pisać proste funkcje testowe. Dla bardziej zaawansowanego testowania popularne są narzędzia stron trzecich, takie jak `bats-core`.

### Podstawowy przykład testu w czystym Bashu:
```bash
function test_example_function {
  result=$(your_function 'test_input')
  expected_output="expected_output"
  
  if [[ "$result" == "$expected_output" ]]; then
    echo "Test zakończony sukcesem."
    return 0
  else
    echo "Test nieudany. Oczekiwano '$expected_output', otrzymano '$result'"
    return 1
  fi
}

# Wywołanie funkcji testowej
test_example_function
```
Przykładowe wyjście:
```
Test zakończony sukcesem.
```

### Używanie `bats-core` do testowania:
Najpierw zainstaluj `bats-core`. Zwykle można to zrobić za pomocą menedżera pakietów lub klonując jego repozytorium.

Następnie napisz swoje testy w oddzielnych plikach `.bats`.

```bash
# Plik: example_function.bats

#!/usr/bin/env bats

@test "test przykładowej funkcji" {
  result="$(your_function 'test_input')"
  expected_output="expected_output"
  
  [ "$result" == "$expected_output" ]
}
```
Aby uruchomić swoje testy, wystarczy wykonać plik `.bats`:
```bash
bats example_function.bats
```
Przykładowe wyjście:
```
 ✓ test przykładowej funkcji

1 test, 0 porażek
```

To podejście pozwala na łatwe zintegrowanie testowania z twoim procesem tworzenia oprogramowania, zapewniając niezawodność i stabilność twoich skryptów Bash.
