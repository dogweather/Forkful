---
aliases:
- /pl/ruby/comparing-two-dates/
date: 2024-01-20 17:33:37.504423-07:00
description: "Por\xF3wnywanie dw\xF3ch dat to sprawdzanie, kt\xF3ra data jest wcze\u015B\
  niejsza, p\xF3\u017Aniejsza lub czy s\u0105 identyczne. Programi\u015Bci robi\u0105\
  \ to, aby obs\u0142u\u017Cy\u0107 terminy,\u2026"
lastmod: 2024-02-18 23:08:50.137852
model: gpt-4-1106-preview
summary: "Por\xF3wnywanie dw\xF3ch dat to sprawdzanie, kt\xF3ra data jest wcze\u015B\
  niejsza, p\xF3\u017Aniejsza lub czy s\u0105 identyczne. Programi\u015Bci robi\u0105\
  \ to, aby obs\u0142u\u017Cy\u0107 terminy,\u2026"
title: "Por\xF3wnywanie dw\xF3ch dat"
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Porównywanie dwóch dat to sprawdzanie, która data jest wcześniejsza, późniejsza lub czy są identyczne. Programiści robią to, aby obsłużyć terminy, wydarzenia i logikę związaną z czasem w aplikacjach.

## How to: (Jak to zrobić:)
```Ruby
require 'date'

date1 = Date.parse("2023-04-15")
date2 = Date.parse("2023-04-18")

if date1 < date2
  puts "date1 jest wcześniejsza niż date2"
elsif date1 > date2
  puts "date1 jest późniejsza niż date2"
else
  puts "date1 jest taka sama jak date2"
end
```
Sample output:
```
date1 jest wcześniejsza niż date2
```

## Deep Dive (Dogłębna analiza)
Porównywanie dat w Ruby działa dzięki klasie `Date` z modułu `date`, który daje wiele metod do manipulowania i porównywania dat. W przeszłości używano do tego gemów zewnętrznych jak np. `time_diff` lub `chronic`. Ruby 1.9 zaczął standardowo oferować te funkcjonalności. Alternatywnie, można używać klasy `Time` do uwzględnienia czasu. Implementacja porównywania dat opiera się na przeliczaniu dat na liczby sekund od ustalonego punktu w czasie (np. epoki Unixowej), a potem porównywaniu tych wartości.

## See Also (Zobacz również)
- Ruby's Time class documentation: [Time](https://ruby-doc.org/core/Time.html)
- Gems for time manipulation like [Active Support's Time Extensions](https://api.rubyonrails.org/classes/ActiveSupport/TimeWithZone.html)
