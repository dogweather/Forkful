---
title:                "Znalezienie długości ciągu znaków"
date:                  2024-01-20T17:48:39.567063-07:00
model:                 gpt-4-1106-preview
simple_title:         "Znalezienie długości ciągu znaków"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/typescript/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Co i dlaczego? Znalezienie długości łańcucha znaków to nic innego, jak ustalenie, ile znaków zawiera dana fraza lub zdanie. Programiści robią to, by weryfikować wpisy użytkowników, dostosować wyświetlanie tekstu, bądź po prostu operować danymi tekstowymi efektywnie.

## How to:
Poniżej znajdziesz przykładowy kod w TypeScript, który pokazuje, jak sprawdzić długość stringa:

```TypeScript
let greeting: string = "Cześć, jak się masz?";
console.log(greeting.length); // Wyświetla długość napisu
```

Sample output:
```
21
```

Możesz też użyć tej właściwości do warunków:
```TypeScript
if (greeting.length > 10) {
    console.log("To dość długi tekst!");
} else {
    console.log("Tekst jest krótki.");
}
```

Sample output:
```
To dość długi tekst!
```

## Deep Dive
Zagłębiając się w temat, `.length` jest właściwością obiektów `String` w JavaScript, odziedziczoną przez TypeScript. Nie od zawsze było to takie łatwe – w przeszłości, w niektórych językach programowania, musiałeś przechodzić przez tekst znak po znaku, by policzyć długość. 

Inną metodą była rozbudowana funkcja, która zajmowała więcej czasu i pamięci. TypeScript (i JavaScript) robi to za Ciebie, przechowując długość jako oddzielne pole w obiekcie string.

Warto pamiętać, że JavaScript używa modelu UTF-16 do reprezentacji stringów. To oznacza, że niektóre "złożone" znaki mogą być postrzegane jako dwie "jednostki kodu" i podwójnie liczone w długości.

Przykład z "złożonymi" znakami:
```TypeScript
let fancyString: string = "𩷶";
console.log(fancyString.length); // Możesz się spodziewać 1, ale wynik to:
```

Sample output:
```
2
```

Zaskoczony? To dlatego, że niektóre znaki wymagają więcej niż jednego kodu UTF-16.

## See Also
Szukasz więcej informacji? Zajrzyj tutaj:
- [Mozilla Developer Network - String.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- [TypeScript Official Documentation](https://www.typescriptlang.org/docs/)
- [Unicode - a deep dive into characters in JS](https://dmitripavlutin.com/what-every-javascript-developer-should-know-about-unicode/)
