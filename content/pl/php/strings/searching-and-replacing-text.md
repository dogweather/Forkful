---
date: 2024-01-20 17:58:24.683887-07:00
description: "Szukanie i zamiana tekstu to chleb powszedni w programowaniu: lokalizujemy\
  \ fragmenty ci\u0105g\xF3w znak\xF3w i podmieniamy je na inne. Czemu? By automatycznie\u2026"
lastmod: '2024-03-13T22:44:35.481525-06:00'
model: gpt-4-1106-preview
summary: "Szukanie i zamiana tekstu to chleb powszedni w programowaniu: lokalizujemy\
  \ fragmenty ci\u0105g\xF3w znak\xF3w i podmieniamy je na inne."
title: Wyszukiwanie i zamiana tekstu
weight: 10
---

## How to: (Jak to zrobić?)
W PHP szukanie i zamiana tekstu często przechodzi przez `str_replace` albo regex z `preg_replace`. Prosty przykład:

```PHP
<?php
$tekst = "Witaj, świecie!";
$szukaj = "świecie";
$zamien_na = "kodzie PHP";

$nowy_tekst = str_replace($szukaj, $zamien_na, $tekst);
echo $nowy_tekst; // Wyświetli 'Witaj, w kodzie PHP!'
?>
```

A teraz regex dla bardziej złożonych przypadków:

```PHP
<?php
$tekst = "Zarejestruj się na kurs PHP w 2023!";
$pattern = "/PHP w [0-9]{4}/";
$zamien_na = "PHP w 2024";

$nowy_tekst = preg_replace($pattern, $zamien_na, $tekst);
echo $nowy_tekst; // Wyświetli 'Zarejestruj się na kurs PHP w 2024!'
?>
```

## Deep Dive (Głębsze zanurzenie)
Szukanie i zamiana tekstu ma długą historię, która zaczyna się wraz z narodzinami programowania. W PHP, `str_replace` jest proste i szybkie dla prostych ciągów znaków, ale nie radzi sobie z patternami i wyrażeniami regularnymi. Dlatego `preg_replace` na ratunek – potężne narzędzie z Perl Compatible Regular Expressions. Często to overkill dla prostych zadanek, ale kiedy trzeba, robi robotę z klasą.

Alternatywy? Można użyć `strtr` jeśli zamiany są bardzo proste, albo `strpos` i `substr_replace` dla bardziej kontrolowanego cięcia i szycia tekstu.

Robota z wyrażeniami regularnymi to nie tylko `preg_replace` – mamy też `preg_match` do wyszukiwania, `preg_split` do dzielenia. Regularni wyjadacze mają nawet swoją syntaksę i możliwości jak backreferences czy lookaround assertions.

## See Also (Zobacz również)
- Oficjalna dokumentacja PHP dla [str_replace](https://www.php.net/manual/en/function.str-replace.php) i [preg_replace](https://www.php.net/manual/en/function.preg-replace.php)
- Interaktywny tester wyrażeń regularnych: [RegExr](https://regexr.com/)
- Tutorial PHP na [PHP.net](https://www.php.net/manual/en/langref.php)
- Przewodnik po wyrażeniach regularnych na [Regular-Expressions.info](https://www.regular-expressions.info/php.html)
