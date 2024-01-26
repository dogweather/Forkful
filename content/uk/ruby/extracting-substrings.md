---
title:                "Виділення підрядків"
date:                  2024-01-20T17:47:12.578383-07:00
model:                 gpt-4-1106-preview
simple_title:         "Виділення підрядків"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/ruby/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why? (Що та Навіщо?)
**Витягування підрядків** - це процес отримання частини тексту з більшого рядка. Програмісти роблять це для аналізу тексту, даних чи просто для редагування змісту.

## How to: (Як це зробити)
```Ruby
# Використання методу slice для отримання підрядка
string = "Привіт, Ruby!"
substring = string.slice(0, 7) # Взяти перші 7 символів
puts substring
# => Привіт,

# Альтернативний спосіб з оператором діапазону
substring2 = string[0..6] # Те ж саме, що і вище
puts substring2
# => Привіт,

# Використання методу slice зі знаком оклику для модифікації оригінального рядка
string.slice!(0..6) # Видаляє вибране з оригінального рядка
puts string
# => Ruby!
```

## Deep Dive (Поглиблений Розбір)
У Ruby, значення рядків завжди було ключовим аспектом через його зосередженість на "приємність для програмістів". Методи витягування підрядків як `slice`, `slice!`, і діапазони (`[x..y]`) існують щоб полегшити цю задачу. Існує безліч альтернатив, таких як `sub`, `gsub`, і `partition`, кожен з яких має своє призначення. Наприклад, `sub` замінить лише перше співпадіння, тоді як `gsub` - усі. 
Що стосується впровадження, підрядки в Ruby є новими рядковими об'єктами, і коли ви міняєте оригінал, це не впливається на підрядок, який ви створили до цього.

## See Also (Дивись також)
- Ruby Docs for String: [String](https://ruby-doc.org/core/String.html)
- "The Well-Grounded Rubyist" by David A. Black – глава про роботу з рядками. 
- Ruby Style Guide: [Substring Extraction](https://rubystyle.guide/#substring)
