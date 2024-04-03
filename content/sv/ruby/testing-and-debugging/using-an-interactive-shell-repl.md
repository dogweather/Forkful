---
date: 2024-01-26 04:17:24.407303-07:00
description: "Ett interaktivt skal, eller REPL (Read-Eval-Print Loop), l\xE5ter dig\
  \ testa kod i realtid. Programmerare anv\xE4nder det f\xF6r att experimentera, fels\xF6\
  ka och l\xE4ra\u2026"
lastmod: '2024-03-13T22:44:38.432569-06:00'
model: gpt-4-0125-preview
summary: "Ett interaktivt skal, eller REPL (Read-Eval-Print Loop), l\xE5ter dig testa\
  \ kod i realtid."
title: "Anv\xE4nda en interaktiv skal (REPL)"
weight: 34
---

## Hur man:
Ruby's REPL kallas IRB (Interactive Ruby). Hoppa in och testa Ruby direkt från din terminal:

```Ruby
irb
2.7.0 :001 > puts "Hej, Ruby-världen!"
Hej, Ruby-världen!
 => nil
2.7.0 :002 > 5.times { print "Ruby! " }
Ruby! Ruby! Ruby! Ruby! Ruby!  => 5
```

## Djupdykning
Introducerad i Ruby 1.8, är IRB ett måste för Rubyister. Det är inspirerat av de interaktiva skalen från Lisp och Python, och kombinerar experiment med omedelbar återkoppling. Alternativ som Pry erbjuder fler funktioner som syntaxmarkering och en robustare felsökningsmiljö. IRB i sig är enkelt, men kan utökas med gems som 'irbtools' för att utöka funktionaliteten. Hur IRB hanterar läs-eval-print-loopen är genom att läsa varje rad av input, utvärdera den som Ruby-kod och sedan skriva ut resultatet, och loopa denna process tills utgång.

## Se också
- [Ruby's IRB](https://ruby-doc.org/stdlib-2.7.0/libdoc/irb/rdoc/IRB.html)
- [Gemet irbtools](https://github.com/janlelis/irbtools)
