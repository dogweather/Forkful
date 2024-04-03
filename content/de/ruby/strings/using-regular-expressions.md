---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:18:02.615556-07:00
description: "Regul\xE4re Ausdr\xFCcke (regex) in Ruby sind Muster, die verwendet\
  \ werden, um Zeichenkombinationen in Strings zu finden. Sie erm\xF6glichen es Entwicklern,\
  \ Text\u2026"
lastmod: '2024-03-13T22:44:54.388161-06:00'
model: gpt-4-0125-preview
summary: "Regul\xE4re Ausdr\xFCcke (regex) in Ruby sind Muster, die verwendet werden,\
  \ um Zeichenkombinationen in Strings zu finden."
title: "Regul\xE4re Ausdr\xFCcke verwenden"
weight: 11
---

## Wie geht das:


### Einfaches Matching
Um einen String gegen ein einfaches Muster abzugleichen, können Sie die `match` Methode verwenden. Unten prüfen wir, ob das Wort "Ruby" in einem gegebenen String existiert.

```ruby
if /Ruby/.match("Hallo, Ruby!")
  puts "Übereinstimmung gefunden!"
end
# Ausgabe: Übereinstimmung gefunden!
```

### Musterabgleich mit Variablen
Sie können Variablen in Ihren Regex interpolieren, indem Sie die `#{}` Syntax verwenden, was Ihre Muster dynamisch macht.

```ruby
language = "Ruby"
if /#{language}/.match("Programmieren in Ruby macht Spaß.")
  puts "Sprechen über Ruby!"
end
# Ausgabe: Sprechen über Ruby!
```

### Verwendung von Regex zur Substitution
Die `gsub` Methode erlaubt es Ihnen, jedes Vorkommen eines Musters mit einem bestimmten Ersatzstring zu ersetzen.

```ruby
puts "foobarfoo".gsub(/foo/, "bar")
# Ausgabe: barbarbar
```

### Erfassung
Klammern in einem Regex werden verwendet, um Teile einer Übereinstimmung zu erfassen. Die `match` Methode gibt ein `MatchData` Objekt zurück, das Sie nutzen können, um Zugriff auf Erfassungen zu bekommen.

```ruby
match_data = /(\w+): (\d+)/.match("Alter: 30")
puts match_data[1] # Erfasstes Label
puts match_data[2] # Erfasster Wert
# Ausgabe:
# Alter
# 30
```

### Verwendung von Drittanbieter-Bibliotheken
Obwohl die Standardbibliothek von Ruby leistungsfähig ist, benötigen Sie manchmal spezialisiertere Funktionalitäten. Ein beliebtes Gem für die Arbeit mit Regex ist `Oniguruma`, das zusätzliche Regex-Funktionen über die eingebaute Ruby Regex-Engine hinaus bietet.

Installieren Sie es mit:
```bash
gem install oniguruma
```

Eine Beispielverwendung könnte so aussehen (angenommen, Sie haben `oniguruma` nach der Installation eingebunden):

```ruby
# Dies ist ein fortgeschritteneres Beispiel und könnte zusätzliche Einrichtung erfordern
require 'oniguruma'

pattern = Oniguruma::ORegexp.new('(\d+)')
match_data = pattern.match("Die Zahl ist 42.")
puts match_data[1]
# Ausgabe: 42
```

Denken Sie daran, dass reguläre Ausdrücke, obwohl mächtig, komplex und schwer zu verwalten werden können für kompliziertere Muster. Streben Sie nach Lesbarkeit und erwägen Sie alternative Methoden, falls Ihr Regex zu kompliziert wird.
