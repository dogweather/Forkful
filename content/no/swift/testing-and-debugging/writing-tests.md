---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:01.333725-07:00
description: "\xC5 skrive tester i Swift inneb\xE6rer \xE5 lage og utf\xF8re kode\
  \ som verifiserer korrektheten av andre kodeenheter i applikasjonen din. Programmerere\
  \ gj\xF8r dette\u2026"
lastmod: '2024-03-13T22:44:41.145465-06:00'
model: gpt-4-0125-preview
summary: "\xC5 skrive tester i Swift inneb\xE6rer \xE5 lage og utf\xF8re kode som\
  \ verifiserer korrektheten av andre kodeenheter i applikasjonen din."
title: Skrive tester
weight: 36
---

## Hvordan:
Swift støtter testing gjennom sitt XCTest-rammeverk, som er integrert i Xcode. Du kan skrive enhetstester for å verifisere individuelle deler av koden din, for eksempel en funksjon som beregner summen av to tall.

```swift
import XCTest
@testable import YourApp

class YourAppTests: XCTestCase {

    func testSum() {
        let result = Calculator().sum(a: 1, b: 2)
        XCTAssertEqual(result, 3, "Summefunksjonen returnerte ikke den forventede verdien.")
    }
}
```

For å kjøre denne testen vil du vanligvis trykke Command-U i Xcode. Utdataen i Xcode-testnavigatoren vil fortelle deg om testen besto eller feilet.

For eksempel en vellykket testutdata:
```
Test Case '-[YourAppTests testSum]' passed (0.005 seconds).
```

For mer avanserte testsenarioer kan du ta i bruk tredjeparts biblioteker som Quick/Nimble, som tilbyr en mer uttrykksfull syntaks for å skrive tester.

Med Quick/Nimble kan du skrive samme test slik:

```swift
// Legg til Quick og Nimble i din Swift pakkebehandler eller bruk CocoaPods/Carthage for å installere dem
import Quick
import Nimble
@testable import YourApp

class CalculatorSpec: QuickSpec {
    override func spec() {
        describe("Calculator") {
            context("når man summerer tall") {
                it("skal returnere den korrekte summen") {
                    let calculator = Calculator()
                    expect(calculator.sum(a: 1, b: 2)).to(equal(3))
                }
            }
        }
    }
}
```

Å kjøre denne testen ville gitt deg lignende utdata i din testkonsoll eller CI/CD-verktøyets logg, som indikerer om testen lyktes eller feilet, med et mer leselig format for å beskrive tester og forventninger.
