---
date: 2024-01-20 17:39:16.184363-07:00
description: "\u041A\u043E\u043B\u0438 \u043C\u0438 \u043A\u0430\u0436\u0435\u043C\
  \u043E \u043F\u0440\u043E \u043F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\
  \u043D\u043D\u044F \u0440\u044F\u0434\u043A\u0430 \u0432 \u043D\u0438\u0436\u043D\
  \u0456\u0439 \u0440\u0435\u0433\u0456\u0441\u0442\u0440, \u043C\u0430\u0454\u043C\
  \u043E \u043D\u0430 \u0443\u0432\u0430\u0437\u0456 \u0437\u043C\u0456\u043D\u0443\
  \ \u0432\u0441\u0456\u0445 \u0432\u0435\u043B\u0438\u043A\u0438\u0445 \u043B\u0456\
  \u0442\u0435\u0440 \u043D\u0430 \u043C\u0430\u043B\u0435\u043D\u044C\u043A\u0456\
  . \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0440\u043E\
  \u0431\u043B\u044F\u0442\u044C \u0446\u0435 \u0434\u043B\u044F \u0443\u043D\u0456\
  \u0444\u0456\u043A\u0430\u0446\u0456\u0457 \u0442\u0435\u043A\u0441\u0442\u0443\u2026"
lastmod: '2024-03-13T22:44:50.200778-06:00'
model: gpt-4-1106-preview
summary: "\u041A\u043E\u043B\u0438 \u043C\u0438 \u043A\u0430\u0436\u0435\u043C\u043E\
  \ \u043F\u0440\u043E \u043F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\
  \u043D\u044F \u0440\u044F\u0434\u043A\u0430 \u0432 \u043D\u0438\u0436\u043D\u0456\
  \u0439 \u0440\u0435\u0433\u0456\u0441\u0442\u0440, \u043C\u0430\u0454\u043C\u043E\
  \ \u043D\u0430 \u0443\u0432\u0430\u0437\u0456 \u0437\u043C\u0456\u043D\u0443 \u0432\
  \u0441\u0456\u0445 \u0432\u0435\u043B\u0438\u043A\u0438\u0445 \u043B\u0456\u0442\
  \u0435\u0440 \u043D\u0430 \u043C\u0430\u043B\u0435\u043D\u044C\u043A\u0456."
title: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F \u0440\
  \u044F\u0434\u043A\u0430 \u0443 \u043D\u0438\u0436\u043D\u0456\u0439 \u0440\u0435\
  \u0433\u0456\u0441\u0442\u0440"
weight: 4
---

## Як це зробити:
Ruby робить це просто. Ось приклад того, як змінити рядок на нижній регістр:

```ruby
original_string = "Це ПРИКЛАД Рядка"
lowercase_string = original_string.downcase

puts lowercase_string
```

Це виведе:

```
це приклад рядка
```

А ось якщо вам потрібно змінити лише латиницю:

```ruby
mixed_string = "Ruby 3.1.2 Є Найкращим!"
lowercase_latin = mixed_string.gsub(/[A-Z]/, &:downcase)

puts lowercase_latin
```

Ви отримаєте:

```
ruby 3.1.2 Є Найкращим!
```

## Поглиблений аналіз:
В давні часи, коли комп'ютери лише розвивалися, великий і малий регістри часто трактувалися як різні символи. Це робило текстову обробку складною. З часом, методи як `downcase` стали стандартом в більшості мов програмування, у тому числі і в Ruby.

Варто зазначити, що метод `downcase` працює відмінно з латинськими літерами. Але коли справа доходить до Unicode символів, як то кирилиця, необхідний метод `mb_chars.downcase.to_s`, якщо ви використовуєте Rails. Натомість, в чистому Ruby, можна користуватися бібліотекою 'unicode_utils':

```ruby
require 'unicode_utils/downcase'

original_string = "Це ПРИКЛАД Рядка"
lowercase_string = UnicodeUtils.downcase(original_string)

puts lowercase_string
```

## Дивіться також:
- [Ruby-Doc.org String#downcase](https://ruby-doc.org/core-3.1.2/String.html#method-i-downcase)
- [UnicodeUtils Gem](https://rubygems.org/gems/unicode_utils/versions/1.4.0)
- [Stack Overflow: Convert string to lower case in Ruby](https://stackoverflow.com/questions/4739596/convert-string-to-lower-case-in-ruby)

Прочитайте, експериментуйте, і не бійтеся пробувати нові підходи. Ruby відомий своєю гнучкістю — користуйтесь цим!
