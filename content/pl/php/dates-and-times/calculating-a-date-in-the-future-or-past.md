---
date: 2024-01-20 17:32:14.134465-07:00
description: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci to\
  \ spos\xF3b na ustalenie, jaki dzie\u0144 b\u0119dzie za X dni, lub jaki by\u0142\
  \ Y dni temu. Programi\u015Bci robi\u0105 to, by\u2026"
lastmod: '2024-03-13T22:44:35.510884-06:00'
model: gpt-4-1106-preview
summary: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci to spos\xF3\
  b na ustalenie, jaki dzie\u0144 b\u0119dzie za X dni, lub jaki by\u0142 Y dni temu."
title: "Obliczanie daty w przysz\u0142o\u015Bci lub przesz\u0142o\u015Bci"
weight: 26
---

## Jak to zrobić:
```PHP
<?php
$today = new DateTime(); // Dzisiejsza data

// Dodawanie dni
$interval = new DateInterval('P10D'); // Period: 10 Days
$futureDate = (clone $today)->add($interval);
echo $futureDate->format('Y-m-d') . PHP_EOL; // Przykładowy output: 2023-04-18

// Odejmowanie dni
$pastDate = (clone $today)->sub($interval);
echo $pastDate->format('Y-m-d') . PHP_EOL; // Przykładowy output: 2023-03-29
?>
```
Możesz zmienić 'P10D' na odpowiednią wartość, żeby uzyskać dokładną datę, której potrzebujesz.

## Głębsze spojrzenie:
PHP ma wbudowane klasy jak `DateTime` i `DateInterval`, które ułatwiają zarządzanie datami. Klasa `DateTime` zastąpiła starsze funkcje jak `strtotime` i `mktime`, oferując obiektowy sposób na manipulację datami. Alternatywą może być stosowanie bibliotek zewnętrznych jak Carbon dla PHP, która rozszerza możliwości `DateTime`.

Obliczanie daty w przeszłości lub przyszłości wymaga uwzględnienia zmian strefy czasowej oraz przestępności lat. PHP radzi sobie z tym za nas, ale dobrze jest o tym pamiętać, szczególnie przy międzynarodowych aplikacjach.

Klonowanie obiektu `DateTime` przed modyfikacją jest istotne, aby nie zmieniać oryginalnej instancji. Jest to szczególnie ważne, gdy chcemy zachować punkt odniesienia i różne daty do porównania.

## Zobacz również:
- Oficjalna dokumentacja PHP dla klasy `DateTime`: https://www.php.net/manual/en/class.datetime.php
- Dokumentacja dla `DateInterval`: https://www.php.net/manual/en/class.dateinterval.php
- Biblioteka Carbon dla PHP: https://carbon.nesbot.com/docs/
- PHP manual na temat obsługi dat i czasu: https://www.php.net/manual/en/book.datetime.php
