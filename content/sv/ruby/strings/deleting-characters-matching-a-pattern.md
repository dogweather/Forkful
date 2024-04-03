---
date: 2024-01-20 17:43:08.134217-07:00
description: "I Ruby kan du rensa str\xE4ngar fr\xE5n o\xF6nskade tecken genom att\
  \ matcha dem mot ett m\xF6nster. Programmerare g\xF6r detta f\xF6r att st\xE4da\
  \ data, validera input eller\u2026"
lastmod: '2024-03-13T22:44:38.412772-06:00'
model: gpt-4-1106-preview
summary: "I Ruby kan du rensa str\xE4ngar fr\xE5n o\xF6nskade tecken genom att matcha\
  \ dem mot ett m\xF6nster."
title: "Ta bort tecken som matchar ett m\xF6nster"
weight: 5
---

## How to:
I Ruby använder du `String#gsub` och `String#delete` för att ta bort tecken som matchar ett mönster. Här är några exempel:

```Ruby
# Använda gsub för att ta bort alla siffror från en sträng
str = "Bilmärke 2020"
puts str.gsub(/\d/, '')  # Output: "Bilmärke "

# Använda delete för att ta bort specifika tecken
str = "hello#%world!"
puts str.delete("#%")    # Output: "helloworld!"
```

`gsub` kan använda reguljära uttryck, så det är kraftfullt och flexibelt. Medan `delete` är snabb och enkel när du vet exakt vilka tecken du vill ta bort.

## Deep Dive:
Att bearbeta strängar är grundläggande i programmering. I Ruby, som skapades 1995 av Yukihiro Matsumoto, fick vi `String#gsub` och `String#delete` som en del av dess rika API för att hantera text.

`String#gsub` står för "global substitution" och ersätter alla förekomster som matchar ett mönster. Eftersom det kan ta reguljära uttryck, kan det vara både en fördel och en nackdel — kraftfull men potentiellt långsammare och svårare att läsa.

`String#delete` är direktare och snabbare men mindre flexibelt. Det tar helt enkelt en lista av tecken som ska tas bort.

Som alternativ när prestanda är avgörande kan vi använda `String#tr` som utför teckenersättning och `String#squeeze` som reducerar duplicerade tecken.

## See Also:
- Ruby's officiella dokumentation för [String#gsub](https://ruby-doc.org/core-3.1.0/String.html#method-i-gsub) och [String#delete](https://ruby-doc.org/core-3.1.0/String.html#method-i-delete)
- Tutorial om reguljära uttryck i Ruby: [Rubular](http://rubular.com/)
