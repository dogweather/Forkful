---
aliases:
- /pl/ruby/checking-if-a-directory-exists/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:17.875876-07:00
description: "Sprawdzanie, czy katalog istnieje w Ruby, pozwala programistom na weryfikacj\u0119\
  \ obecno\u015Bci katalogu przed wykonaniem operacji takich jak odczytywanie plik\xF3\
  w\u2026"
lastmod: 2024-02-18 23:08:50.139749
model: gpt-4-0125-preview
summary: "Sprawdzanie, czy katalog istnieje w Ruby, pozwala programistom na weryfikacj\u0119\
  \ obecno\u015Bci katalogu przed wykonaniem operacji takich jak odczytywanie plik\xF3\
  w\u2026"
title: Sprawdzanie, czy katalog istnieje
---

{{< edit_this_page >}}

## Co i Dlaczego?
Sprawdzanie, czy katalog istnieje w Ruby, pozwala programistom na weryfikację obecności katalogu przed wykonaniem operacji takich jak odczytywanie plików czy tworzenie nowych katalogów. Jest to kluczowe dla uniknięcia błędów w obsłudze plików i zapewnienia niezawodności manipulacji systemem plików.

## Jak to zrobić:
Standardowa biblioteka Ruby oferuje proste metody do sprawdzania, czy katalog istnieje. Oto jak to zrobić czystym Ruby, bez potrzeby korzystania z bibliotek stron trzecich:

```ruby
require 'fileutils'

# Sprawdź, czy katalog istnieje
if Dir.exist?('/ścieżka/do/katalogu')
  puts 'Katalog istnieje.'
else
  puts 'Katalog nie istnieje.'
end
```
Przykładowy wynik:
```
Katalog istnieje.
```
Lub:
```
Katalog nie istnieje.
```

Oprócz użycia `Dir.exist?`, możesz również wykorzystać metodę `File.directory?`, która zwraca `true`, jeśli podana ścieżka jest katalogiem:

```ruby
if File.directory?('/ścieżka/do/katalogu')
  puts 'Katalog istnieje.'
else
  puts 'Katalog nie istnieje.'
end
```
Obie `Dir.exist?` i `File.directory?` są częścią standardowej biblioteki Ruby i nie wymagają żadnych zewnętrznych gemów do użycia, co czyni je wygodnymi i efektywnymi opcjami do sprawdzania katalogów.
