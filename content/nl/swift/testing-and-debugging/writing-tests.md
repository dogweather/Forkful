---
title:                "Tests Schrijven"
aliases:
- /nl/swift/writing-tests/
date:                  2024-01-28T22:13:07.719599-07:00
model:                 gpt-4-0125-preview
simple_title:         "Tests Schrijven"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/swift/writing-tests.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Tests schrijven is het creëren van code die controleert of je software werkt zoals gepland. Programmeurs testen om bugs vroeg te vangen, kwaliteit te waarborgen en het onderhoud te vereenvoudigen.

## Hoe:
Swift gebruikt het XCTest-framework voor het testen. Hier is een eenvoudige test voor een functie `add(a:b:)`:

```Swift
import XCTest

class MathTests: XCTestCase {

    func testAdd() {
        let resultaat = add(a: 2, b: 3)
        XCTAssertEqual(resultaat, 5, "Verwacht dat 2 + 3 gelijk is aan 5")
    }

    func add(a: Int, b: Int) -> Int {
        return a + b
    }
}
```
Voer tests uit met Xcode's Test Navigator of gebruik `cmd+U`. De uitvoer moet lezen:

```plaintext
Test Suite 'Alle tests' geslaagd op ...
    1 test uitgevoerd, met 0 fouten (0 onverwacht) in 0.001 (0.004) seconden
```

## Diepgaand
XCTest, onderdeel van Xcode sinds 2013, nam het stokje over van OCUnit. Alternatieven zijn Quick (BDD-framework) en SnapshotTesting (UI-tests). De implementatie van testen vertrouwt op beweringsfuncties, testgevallen en eventueel testsuites, waarbij gebruik wordt gemaakt van de mogelijkheden van het XCTest-framework.

## Zie ook
- [Overzicht van Apple XCTest](https://developer.apple.com/documentation/xctest)
- [iOS Unit Testing en UI Testing Tutorial van Ray Wenderlich](https://www.raywenderlich.com/21020457-ios-unit-testing-and-ui-testing-tutorial)
- [Swift-code testen met Quick](https://github.com/Quick/Quick)
- [SnapshotTesting op GitHub](https://github.com/pointfreeco/swift-snapshot-testing)
