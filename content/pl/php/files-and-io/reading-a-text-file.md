---
date: 2024-01-20 17:54:57.683300-07:00
description: "Czytanie pliku tekstowego to proces pobierania danych zawartych w pliku\
  \ tekstowym do dalszego przetwarzania. Programi\u015Bci robi\u0105 to, by obs\u0142\
  ugiwa\u0107\u2026"
lastmod: '2024-03-13T22:44:35.514941-06:00'
model: gpt-4-1106-preview
summary: Czytanie pliku tekstowego to proces pobierania danych zawartych w pliku tekstowym
  do dalszego przetwarzania.
title: Odczytywanie pliku tekstowego
weight: 22
---

## Jak to zrobić:
```PHP
<?php
// Otwieramy plik 'przykladowy.txt' w trybie tylko do odczytu
$plik = fopen('przykladowy.txt', 'r');

// Czytamy całą zawartość pliku do zmiennej $zawartosc
$zawartosc = fread($plik, filesize('przykladowy.txt'));

// Wyświetlamy zawartość
echo $zawartosc;

// Zamykamy plik
fclose($plik);
?>
```

## Deep Dive
Historia czytania plików tekstowych w językach programowania jest tak stara jak same języki. Alternatywą dla `fopen()` i `fread()` w PHP jest użycie funkcji `file_get_contents()`, która skróci kod:

```PHP
<?php
$zawartosc = file_get_contents('przykladowy.txt');
echo $zawartosc;
?>
```

Ale czym się różnią te metody? Używając `fopen()`, możemy precyzyjnie kontrolować, jak dużo danych czytamy z pliku oraz reagować na błędy podczas otwierania pliku. `file_get_contents()` jest proste i szybkie, ale mniej elastyczne.

## Zobacz również
- Tutorial do głębszego zanurzenia się w temat: [PHP: The Right Way](https://phptherightway.com/#files)
