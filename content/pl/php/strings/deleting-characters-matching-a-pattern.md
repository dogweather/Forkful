---
date: 2024-01-20 17:42:42.774548-07:00
description: "Usuwanie znak\xF3w odpowiadaj\u0105cych okre\u015Blonemu wzorcowi to\
  \ po prostu filtrowanie tekstu. Programi\u015Bci robi\u0105 to, by oczy\u015Bci\u0107\
  \ dane, usun\u0105\u0107 niepotrzebne\u2026"
lastmod: '2024-03-13T22:44:35.480589-06:00'
model: gpt-4-1106-preview
summary: "Usuwanie znak\xF3w odpowiadaj\u0105cych okre\u015Blonemu wzorcowi to po\
  \ prostu filtrowanie tekstu."
title: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca"
weight: 5
---

## Jak to zrobić:
Do usunięcia znaków używa się często wyrażeń regularnych z funkcją `preg_replace`. Oto przykład:

```php
$text = "Witaj, Świecie! 1234";
$pattern = '/[0-9]+/';
$replacement = '';

$cleanedText = preg_replace($pattern, $replacement, $text);

echo $cleanedText; // Wynik: "Witaj, Świecie! "
```

Wyrażenie regularne `[0-9]+` oznacza, że znajdziemy wszystkie miejsca z jednym lub więcej cyframi i zamienimy je na pusty string, czyli usuniemy.

## Deep Dive
Usuwanie znaków to nie tylko `preg_replace`. Historia pokazuje, że w PHP używano też `str_replace` do prostszych zadań, bez wyrażeń regularnych. Alternatywą jest też `filter_var` z flagą `FILTER_SANITIZE_STRING`, ale działa mniej elastycznie. W implementacji `preg_replace` ważne jest, by zrozumieć składnię wyrażeń regularnych – wzorce to klucz do mocy tej funkcji.

## Zobacz także
- [PHP Manual: preg_replace](https://www.php.net/manual/en/function.preg-replace.php)
- [PHP Manual: Regex syntax](https://www.php.net/manual/en/pcre.pattern.php)
- [PHP: str_replace](https://www.php.net/manual/en/function.str-replace.php)
- [PHP: filter_var](https://www.php.net/manual/en/function.filter-var.php)
