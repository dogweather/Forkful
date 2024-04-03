---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:12:55.175508-07:00
description: "Tablice asocjacyjne, znane bardziej jako hashe w Ruby, umo\u017Cliwiaj\u0105\
  \ parowanie unikalnych kluczy z warto\u015Bciami. S\u0105 niezast\u0105pione, kiedy\
  \ potrzebujesz \u015Bledzi\u0107\u2026"
lastmod: '2024-03-13T22:44:35.923789-06:00'
model: gpt-4-0125-preview
summary: "Tablice asocjacyjne, znane bardziej jako hashe w Ruby, umo\u017Cliwiaj\u0105\
  \ parowanie unikalnych kluczy z warto\u015Bciami."
title: Korzystanie z tablic asocjacyjnych
weight: 15
---

## Jak to zrobić:
Tworzenie i używanie hashy w Ruby jest proste. Możesz zainicjalizować pusty hash, wypełnić go parami klucz-wartość, uzyskać dostęp do wartości przez ich klucze i więcej. Oto jak to zrobisz:

```Ruby
# Tworzenie hashy
my_hash = { "name" => "John Doe", "age" => 30 }

# Inny sposób na stworzenie hashy
another_hash = Hash.new
another_hash["position"] = "Developer"

# Dostęp do wartości hashy
puts my_hash["name"] # Wynik: John Doe

# Dodanie nowej pary klucz-wartość
my_hash["language"] = "Ruby"
puts my_hash # Wynik: {"name"=>"John Doe", "age"=>30, "language"=>"Ruby"}

# Iterowanie przez hashę
my_hash.each do |key, value|
  puts "#{key}: #{value}"
end
# Wynik:
# name: John Doe
# age: 30
# language: Ruby
```

Możesz również używać symboli jako bardziej efektywnych kluczy:

```Ruby
# Używanie symboli dla kluczy
symbol_hash = { name: "Jane Doe", age: 22 }
puts symbol_hash[:name] # Wynik: Jane Doe
```

## Pogłębiona analiza:
Koncepcja tablic asocjacyjnych nie jest unikatowa dla Ruby; wiele języków implementuje je pod różnymi nazwami, jak słowniki w Pythonie czy obiekty w JavaScript (kiedy używane jako pary klucz-wartość). We wczesnych etapach Ruby, hashe były nieco wolniejsze i nie tak wszechstronne. Jednak z czasem, implementacja hashy w Ruby stała się bardzo zoptymalizowana, szczególnie dla kluczy symboli, czyniąc je niezwykle efektywnymi dla częstego dostępu i aktualizacji.

Hashi w Ruby wyróżniają się swoją syntaktyczną łatwością użycia i elastycznością - można używać prawie każdego typu obiektu jako klucz, chociaż najczęściej używa się symboli i łańcuchów znaków. Wewnętrznie, hashi w Ruby są implementowane używając algorytmu haszującego, który balansuje między szybkością a efektywnością pamięci, nawet gdy liczba elementów rośnie.

Chociaż hashe są niezwykle wszechstronne, nie są one uniwersalnym rozwiązaniem do przechowywania danych w Ruby. Dla uporządkowanych kolekcji bardziej odpowiednie są tablice, a dla zbiorów unikalnych elementów może lepszy będzie Set. Ponadto, dla bardzo złożonych struktur danych, tworzenie własnych klas może być wskazane.

Pamiętaj, że wybór użycia hashy w porównaniu z innymi strukturami danych w dużej mierze sprowadza się do konkretnego przypadku użycia - hashe sprawdzają się przy szybkich wyszukiwaniach i utrzymywaniu asocjacji między unikalnymi kluczami a ich wartościami.
