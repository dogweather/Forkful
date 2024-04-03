---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:27:55.217255-07:00
description: "Zapisywanie do pliku tekstowego w Fish Shell umo\u017Cliwia trwa\u0142\
  e przechowywanie danych, co u\u0142atwia ich p\xF3\u017Aniejsze pobieranie lub manipulowanie,\
  \ zar\xF3wno przez\u2026"
lastmod: '2024-03-13T22:44:35.860156-06:00'
model: gpt-4-0125-preview
summary: "Zapisywanie do pliku tekstowego w Fish Shell umo\u017Cliwia trwa\u0142e\
  \ przechowywanie danych, co u\u0142atwia ich p\xF3\u017Aniejsze pobieranie lub manipulowanie,\
  \ zar\xF3wno przez ten sam skrypt Fish, jak i inne programy."
title: Pisanie pliku tekstowego
weight: 24
---

## Jak to zrobić:
Aby zapisać do pliku tekstowego w Fish, można użyć polecenia `echo` połączonego z operatorami przekierowania. Nie ma popularnych bibliotek firm trzecich specjalnie do zapisywania plików w Fish, ponieważ wbudowane komendy powłoki są proste i efektywne w tym celu.

### Zapisywanie tekstu do nowego pliku lub nadpisywanie istniejącego pliku:
```fish
echo "Witaj, Fish Shell!" > output.txt
```
To polecenie zapisuje "Witaj, Fish Shell!" do `output.txt`, tworząc plik, jeśli nie istnieje, lub nadpisując go, jeśli istnieje.

### Dopisywanie tekstu do istniejącego pliku:
Jeśli chcesz dodać tekst na końcu istniejącego pliku, nie usuwając jego obecnej zawartości, użyj operatora do dopisywania `>>`:
```fish
echo "Dodaję nowy wiersz do pliku." >> output.txt
```

### Zapisywanie wielu wierszy:
Można zapisać wiele wierszy do pliku, używając echo z znakiem nowej linii `\n`, lub można połączyć kilka poleceń echo razem, używając średników:
```fish
echo "Pierwsza linia\nDruga linia" > output.txt
# LUB
echo "Pierwsza linia" > output.txt; echo "Druga linia" >> output.txt
```

### Przykładowa zawartość:
Aby zobaczyć zawartość `output.txt` po uruchomieniu powyższych poleceń, użyj polecenia `cat`:
```fish
cat output.txt
```
```plaintext
Pierwsza linia
Druga linia
```
Zamiana lub dopisywanie tekstów, jak pokazano, manipuluje zawartością pliku zgodnie z twoimi wymaganiami, demonstrując proste, a jednak potężne sposoby pracy z plikami tekstowymi w Fish Shell.
