---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:26.376529-07:00
description: "Pisanie do standardowego b\u0142\u0119du (stderr) w Ruby polega na kierowaniu\
  \ komunikat\xF3w o b\u0142\u0119dach lub informacji diagnostycznych do oddzielnego\
  \ strumienia\u2026"
lastmod: '2024-03-13T22:44:35.948700-06:00'
model: gpt-4-0125-preview
summary: "Pisanie do standardowego b\u0142\u0119du (stderr) w Ruby polega na kierowaniu\
  \ komunikat\xF3w o b\u0142\u0119dach lub informacji diagnostycznych do oddzielnego\
  \ strumienia wyj\u015Bciowego, r\xF3\u017Cnego od standardowego wyj\u015Bcia (stdout)."
title: "Pisanie do standardowego b\u0142\u0119du"
weight: 25
---

## Jak to zrobić:
Standardowa biblioteka Ruby'ego zapewnia prosty sposób na zapis do stderr za pomocą `$stderr` lub `STDERR`. Nie potrzebujesz bibliotek stron trzecich do tej podstawowej operacji.

### Zapisywanie prostej wiadomości do stderr:
```ruby
$stderr.puts "Błąd: Nie znaleziono pliku."
# Lub równoważnie
STDERR.puts "Błąd: Nie znaleziono pliku."
```
Przykładowe wyjście (do stderr):
```
Błąd: Nie znaleziono pliku.
```

### Przekierowywanie stderr do pliku:
```ruby
File.open('error.log', 'w') do |plik|
  STDERR.reopen(plik)
  STDERR.puts "Nie udało się otworzyć konfiguracji."
end
```
Ten fragment kodu przekierowuje stderr do pliku o nazwie `error.log`, a wszystkie kolejne zapisane błędy będą tam wyjściowane aż do zresetowania przekierowania stderr lub zakończenia programu.

### Użycie stderr z obsługą wyjątków:
```ruby
begin
  # Symulacja operacji, która może się nie powieść, np. otwarcie pliku
  File.open('nonexistent_file.txt')
rescue Exception => e
  STDERR.puts "Wystąpił wyjątek: #{e.message}"
end
```
Przykładowe wyjście (do stderr):
```
Wystąpił wyjątek: No such file or directory @ rb_sysopen - nonexistent_file.txt
```

Chociaż wbudowane metody Ruby'ego do pisania do stderr wystarczają dla wielu zastosowań, dla bardziej złożonych potrzeb logowania można rozważyć użycie standardowej biblioteki `logger` lub zewnętrznych gemów takich jak `Log4r`. Zapewniają one konfigurowalne mechanizmy logowania, w tym poziomy ważności, formatowanie i możliwość zapisu do różnych wyjść, w tym do plików, e-maili i innych.
