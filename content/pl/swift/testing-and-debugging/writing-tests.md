---
title:                "Pisanie testów"
aliases:
- /pl/swift/writing-tests/
date:                  2024-02-03T19:32:05.567804-07:00
model:                 gpt-4-0125-preview
simple_title:         "Pisanie testów"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/swift/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?
Pisanie testów w języku Swift polega na tworzeniu i wykonywaniu kodu, który weryfikuje poprawność innych jednostek kodu w aplikacji. Programiści robią to, aby zapewnić niezawodność, wykryć błędy na wczesnym etapie cyklu rozwoju oraz ułatwić przyszłe refaktoryzacje kodu bez niezamierzonych konsekwencji.

## Jak to zrobić:
Swift wspiera testowanie poprzez swoje środowisko XCTest, które jest zintegrowane z Xcode. Można pisać testy jednostkowe w celu weryfikacji indywidualnych części kodu, na przykład funkcji, która oblicza sumę dwóch liczb.

```swift
import XCTest
@testable import TwojaAplikacja

class TestyTwojejAplikacji: XCTestCase {

    func testSumy() {
        let wynik = Kalkulator().suma(a: 1, b: 2)
        XCTAssertEqual(wynik, 3, "Funkcja sumująca nie zwróciła oczekiwanej wartości.")
    }
}
```

Aby uruchomić ten test, zwykle naciska się Command-U w Xcode. Wyjście w nawigatorze testów Xcode powie Ci, czy test przeszedł pomyślnie, czy nie.

Na przykład, pomyślne wyjście testu:
```
Przypadek testowy '-[TestyTwojejAplikacji testSumy]' zakończony sukcesem (0.005 sekund).
```

W przypadku bardziej zaawansowanych scenariuszy testowych możesz korzystać z bibliotek firm trzecich takich jak Quick/Nimble, które oferują bardziej ekspresyjną składnię do pisania testów.

Z Quick/Nimble możesz napisać ten sam test w następujący sposób:

```swift
// Dodaj Quick i Nimble do menedżera pakietów Swift lub użyj CocoaPods/Carthage, aby je zainstalować
import Quick
import Nimble
@testable import TwojaAplikacja

class SpecyfikacjaKalkulatora: QuickSpec {
    override func spec() {
        describe("Kalkulator") {
            context("kiedy sumuje liczby") {
                it("powinien zwrócić poprawną sumę") {
                    let kalkulator = Kalkulator()
                    expect(kalkulator.suma(a: 1, b: 2)).to(equal(3))
                }
            }
        }
    }
}
```

Uruchomienie tego testu dałoby Ci podobne wyjście w konsoli testowej lub logu narzędzia CI/CD, wskazujące, czy test się powiódł czy nie, z bardziej czytelnym formatem opisującym testy i oczekiwania.
