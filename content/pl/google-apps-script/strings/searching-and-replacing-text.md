---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:01:26.662818-07:00
description: "Wyszukiwanie i zast\u0119powanie tekstu w Google Apps Script polega\
  \ na programowym identyfikowaniu konkretnych ci\u0105g\xF3w znak\xF3w w dokumencie,\
  \ arkuszu\u2026"
lastmod: '2024-03-13T22:44:34.884951-06:00'
model: gpt-4-0125-preview
summary: "Wyszukiwanie i zast\u0119powanie tekstu w Google Apps Script polega na programowym\
  \ identyfikowaniu konkretnych ci\u0105g\xF3w znak\xF3w w dokumencie, arkuszu kalkulacyjnym\
  \ lub innym typie zawarto\u015Bci Google Apps i zast\u0119powaniu ich innymi warto\u015B\
  ciami tekstowymi."
title: Wyszukiwanie i zamiana tekstu
weight: 10
---

## Jak to zrobić:
Google Apps Script oferuje prosty sposób na wyszukiwanie i zastępowanie tekstu, zwłaszcza w Google Docs i Arkuszach. Poniżej przykłady dla obu.

### Google Docs:
Aby wyszukać i zastąpić tekst w dokumencie Google, głównie będziesz korzystać z klasy `DocumentApp`.

```javascript
function searchReplaceInDoc() {
  var doc = DocumentApp.getActiveDocument();
  var body = doc.getBody();
  
  // Aby wyszukać i zastąpić konkretną frazę
  body.replaceText('searchText', 'replacementText');
  
  DocumentApp.getActiveDocument().saveAndClose();
}

// Użycie
searchReplaceInDoc();
```

Ten fragment kodu wyszukuje wszystkie wystąpienia `'searchText'` w aktywnym dokumencie Google i zastępuje je `'replacementText'`.

### Google Sheets:
Podobnie, w Arkuszach Google, można użyć `SpreadsheetApp` do przeprowadzenia operacji wyszukiwania i zastępowania:

```javascript
function searchReplaceInSheet() {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  
  // Wyszukaj i zastąp w aktualnie aktywnym arkuszu
  // replaceText(searchText, replacement)
  sheet.createTextFinder('searchText').replaceAllWith('replacementText');
}

// Użycie
searchReplaceInSheet();
```

W tym przykładzie, `createTextFinder('searchText')` wyszukuje w aktywnym arkuszu 'searchText', a `replaceAllWith('replacementText')` zastępuje wszystkie wystąpienia 'replacementText'.

## Szczegółowe rozważania
Funkcjonalność wyszukiwania i zastępowania w Google Apps Script jest mocno związana z jego internetową naturą, co pozwala skryptom na płynną manipulację tekstem w różnych aplikacjach Google. Historycznie, ta możliwość wynika z szerszego kontekstu przetwarzania i manipulacji tekstem w programowaniu, gdzie regularne wyrażenia i funkcje ciągów w językach takich jak Perl i Python ustanowiły wysoki standard elastyczności i mocy.

Chociaż funkcjonalność wyszukiwania i zastępowania w Google Apps Script jest potężna do prostych substytucji, brakuje jej pełnych możliwości regularnych wyrażeń znajdowanych w niektórych innych językach. Na przykład, chociaż można używać podstawowych regularnych wyrażeń w `createTextFinder` w Arkuszach Google, opcje dla skomplikowanego dopasowywania wzorców i manipulacji są ograniczone w porównaniu do Perla czy Pythona.

Dla bardziej zaawansowanych potrzeb przetwarzania tekstu programiści mogą zwrócić się ku eksporcie zawartości Google Docs lub Arkuszy do formatu, który może być przetworzony zewnętrznie z użyciem potężniejszych języków, lub wykorzystując Google Apps Script do wywoływania zewnętrznych API lub usług oferujących bardziej zaawansowane możliwości manipulacji tekstem.

Pomimo tych ograniczeń, dla większości typowych zadań wyszukiwania i zastępowania w ekosystemie aplikacji Google, Google Apps Script oferuje prosty, efektywny i wysoko zintegrowany rozwiązanie dostosowane do potrzeb automatyzacji i skryptowania w ramach pakietu narzędzi produktywnościowych Google.
