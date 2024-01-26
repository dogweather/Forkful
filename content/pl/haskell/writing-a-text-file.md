---
title:                "Zapisywanie pliku tekstowego"
html_title:           "Arduino: Zapisywanie pliku tekstowego"
simple_title:         "Zapisywanie pliku tekstowego"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/haskell/writing-a-text-file.md"
---

{{< edit_this_page >}}

## What & Why?
("Co i Dlaczego?")

Zapisywanie pliku tekstowego to sposób trwałego przechowywania danych. Programiści robią to, by zapisywać ustawienia, dane użytkownika, logi czy po prostu wyniki pracy programów.

## How to:
("Jak to zrobić:")

```Haskell
-- Używamy funkcji 'writeFile', by zapisać tekst do pliku
import System.IO

main :: IO ()
main = do
    let str = "Witaj, Świecie! To jest tekst w pliku."
    writeFile "przyklad.txt" str
```

Sprawdzenie wyniku:

```bash
$ cat przyklad.txt
Witaj, Świecie! To jest tekst w pliku.
```

## Deep Dive:
("Wnikliwe Rozważania:")

Historia: 'writeFile' pochodzi z modułu System.IO, który jest częścią Haskell od wczesnych wersji.

Alternatywy: Można użyć 'appendFile' do dopisania tekstu, 'openFile' z trybami 'ReadMode', 'WriteMode', 'AppendMode', 'ReadWriteMode' dla bardziej szczegółowej kontroli.

Szczegóły implementacji: 'writeFile' używa 'lazy I/O', zapisując dane częściowo, co jest wydajne, ale może prowadzić do niespodzianek, jeśli nie rozumiemy tego modelu.

## See Also:
("Zobacz Także:")

- [Haskell.org dokumentacja System.IO](https://hackage.haskell.org/package/base/docs/System-IO.html)
- [Learn You a Haskell for Great Good! - Input and Output](http://learnyouahaskell.com/input-and-output)
- [Real World Haskell - Working with Files](http://book.realworldhaskell.org/read/io.html)
