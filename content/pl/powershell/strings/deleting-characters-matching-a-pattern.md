---
date: 2024-01-20 17:42:46.626436-07:00
description: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca to zabieg, gdzie wybierasz\
  \ i eliminujesz okre\u015Blone sekwencje tekstu z wi\u0119kszej ca\u0142o\u015B\
  ci. Programi\u015Bci to robi\u0105, aby\u2026"
lastmod: '2024-03-13T22:44:35.611822-06:00'
model: gpt-4-1106-preview
summary: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca to zabieg, gdzie wybierasz\
  \ i eliminujesz okre\u015Blone sekwencje tekstu z wi\u0119kszej ca\u0142o\u015B\
  ci."
title: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca"
weight: 5
---

## Jak to zrobić:
```PowerShell
# Usuwanie cyfr z ciągu znaków
$string = "P0w3r5hell r0ck5!"
$cleanString = $string -replace '[0-9]', ''
$cleanString
```
Wyjście:
```
Pwrhell rcks!
```

```PowerShell
# Usuwanie wszystkich form znaków interpunkcyjnych
$string = "PowerShell, jak zwykle: niesamowity!"
$cleanString = $string -replace '[\p{P}]', ''
$cleanString
```
Wyjście:
```
PowerShell jak zwykle niesamowity
```

## Wnikliwe spojrzenie:
Historia PowerShell rozpoczyna się w 2006 roku, kiedy to został on uwolniony jako bardziej rozbudowany zastępca dla starszych interpreterów wiersza poleceń. Usuwanie znaków według wzorca jest możliwe dzięki silnikowi wyrażeń regularnych, który jest wbudowany w PowerShell. Alternatywy? Możesz użyć funkcji `.Trim()`, `.Replace()` albo zewnętrznych narzędzi jak `sed` w systemie UNIX. Użycie `-replace` w PowerShell jest jednak szybsze i proste dzięki wbudowanemu wsparciu dla wyrażeń regularnych. Wyrażenia regularne używają specjalnej składni do definiowania wzorców tekstowych, co daje programistom potężne narzędzie do obróbki tekstów.

## Zobacz również:
- [about_Regular_Expressions](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.1)
- [Regular Expression Quick Start](https://www.regular-expressions.info/quickstart.html)
