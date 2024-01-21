---
title:                "Zeichenketten verknüpfen"
date:                  2024-01-20T17:35:23.440464-07:00
model:                 gpt-4-1106-preview
simple_title:         "Zeichenketten verknüpfen"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/ruby/concatenating-strings.md"
---

{{< edit_this_page >}}

## Was & Warum?
String-Konkatenation ist das Zusammenführen von zwei oder mehreren Strings zu einem einzigen. Programmierer nutzen das, um Textdynamisch zu generieren oder Inhalte zusammenzufassen.

## How to:
```Ruby
# Einfache Verknüpfung mit '+'
greeting = "Hallo, " + "Welt!"
puts greeting # => Hallo, Welt!

# Mit Variable interpolation und #{}
name = "Ruby"
message = "#{name} macht Spaß!"
puts message # => Ruby macht Spaß!

# Die 'concat' Methode
str = "Ich lerne "
str.concat("Programmieren.")
puts str # => Ich lerne Programmieren.

# '<<' - Der Shovel Operator
str = "Ruby"
str << " " << "Rocks!"
puts str # => Ruby Rocks!
```

## Deep Dive
String-Konkatenation ist so alt wie Programmiersprachen selbst. Historisch gesehen war sie eine der ersten Methoden, um Daten dynamisch in Software zu verarbeiten. In Ruby, wie auch in vielen anderen Sprachen, gibt es mehrere Wege, um Strings zu konkatenieren.

Die Verwendung von '+' ist wohl am direkten, aber nicht immer die effizienteste Methode, besonders wenn es um den Umgang mit sehr vielen oder langen Strings geht. Jeder '+'-Operation erzeugt ein neues String-Objekt, was den Speicher belasten kann.

Durch Interpolation, erkennbar an den `#{}`-Klammern, werden Werte in einen bestehenden String eingesetzt. Sie ist oft lesefreundlicher und performanter als die '+'-Methode.

Die `concat` Methode ist eine direkte Weise, einen String an einen anderen anzuhängen, ohne dabei ein neues Objekt zu erstellen. Ähnlich verhält sich der Shovel Operator `<<`, der häufig in Ruby darauf ausgelegt ist, effizienter zu arbeiten, da er den ursprünglichen String modifiziert, anstatt ein neues Objekt zu erschaffen.

## See Also
- [Ruby-Dokumentation zu Strings](https://ruby-doc.org/core-3.1.2/String.html)
- [Ruby Style Guide](https://github.com/rubocop/ruby-style-guide#strings)
- [Practical Object-Oriented Design in Ruby (Buch von Sandi Metz)](https://www.poodr.com/)