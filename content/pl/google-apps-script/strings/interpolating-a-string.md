---
title:                "Interpolacja ciągu znaków"
aliases:
- /pl/google-apps-script/interpolating-a-string/
date:                  2024-02-01T21:55:48.843186-07:00
model:                 gpt-4-0125-preview
simple_title:         "Interpolacja ciągu znaków"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/google-apps-script/interpolating-a-string.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Interpolacja ciągów w Google Apps Script umożliwia dynamiczne osadzanie wyrażeń w ciągach, ułatwiając tworzenie bardziej czytelnego i łatwiejszego do utrzymania kodu. Programiści używają tej techniki, aby bezproblemowo włączać zmienne i wyrażenia do ciągów bez skomplikowanej składni konkatenacji.

## Jak to zrobić:

W Google Apps Script interpolacja ciągów jest realizowana za pomocą literałów szablonowych. Są to literały ciągów umożliwiające osadzanie wyrażeń, oznaczone za pomocą cudzysłowów zwróconych (\`) zamiast zwykłych cudzysłowów. Oto jak możesz ich używać:

```javascript
// Podstawowy przykład
function basicInterpolationExample() {
  const user = 'Alice';
  console.log(`Cześć, ${user}!`); // Wynik: Cześć, Alice!
}

// Używanie wyrażeń
function expressionInterpolationExample() {
  const a = 5;
  const b = 10;
  console.log(`Pięć plus dziesięć to ${a + b}.`); // Wynik: Pięć plus dziesięć to 15.
}

// Wieloliniowe ciągi
function multiLineStringExample() {
  const item = 'Google Apps Script';
  console.log(`To jest wieloliniowy ciąg:
Cześć wszystkim,
Dziś dyskutujemy o ${item}.`);
  // Wynik:
  // To jest wieloliniowy ciąg:
  // Cześć wszystkim,
  // Dziś dyskutujemy o Google Apps Script.
}

basicInterpolationExample();
expressionInterpolationExample();
multiLineStringExample();
```

Te przykłady ilustrują podstawowe użycie, osadzanie wyrażeń i tworzenie wieloliniowych ciągów z interpolowanymi wartościami.

## Pogłębiona analiza

Literały szablonowe, w tym interpolacja ciągów, zostały wprowadzone w ECMAScript 2015 (ES6) i następnie przyjęte w Google Apps Script. Przed tym programiści musieli polegać wyłącznie na konkatenacji ciągów, co mogło być uciążliwe dla skomplikowanych ciągów lub przy integrowaniu wielu wartości zmiennych.

```javascript
// Stary sposób (przed ES6)
var user = 'Bob';
console.log('Cześć, ' + user + '!');
```

Chociaż interpolacja ciągów jest potężną funkcją, ważne jest, aby być świadomym kontekstów, w których jest używana. Na przykład, bezpośrednie osadzenie danych wejściowych użytkownika bez odpowiedniej sanacji może prowadzić do problemów z bezpieczeństwem, takich jak ataki iniekcji. Deweloperzy Google Apps Script powinni upewnić się, że wszelkie dynamiczne treści interpolowane do ciągów są odpowiednio sprawdzane lub oczyszczone.

W porównaniu do innych języków programowania, koncepcja interpolacji ciągów istnieje powszechnie, z różną składnią. Python używa f-stringów lub metody `format`, Ruby używa `#{}` w podwójnie cytowanych ciągach, a wiele nowoczesnych języków przyjęło podobne funkcje ze względu na czytelność i wygodę, które oferują.

Chociaż Google Apps Script nie oferuje dodatkowych funkcji interpolacji poza tymi, które są dostarczane przez standardy ECMAScript, obecna funkcjonalność jest potężna i wystarczająca dla większości przypadków użycia. Deweloperzy pochodzący z języków z bardziej rozbudowanymi mechanizmami interpolacji mogą potrzebować dostosować swoje oczekiwania, ale prawdopodobnie docenią prostotę i efektywność literałów szablonowych w Google Apps Script.
