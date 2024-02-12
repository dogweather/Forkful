---
title:                "Generierung von Zufallszahlen"
aliases:
- de/fish-shell/generating-random-numbers.md
date:                  2024-01-27T20:33:22.746870-07:00
model:                 gpt-4-0125-preview
simple_title:         "Generierung von Zufallszahlen"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/fish-shell/generating-random-numbers.md"
---

{{< edit_this_page >}}

## Was & Warum?

Das Generieren von Zufallszahlen ist eine grundlegende Aufgabe beim Programmieren, die für alles von der Datenstichprobe bis zur Spielentwicklung verwendet wird. In Fish Shell ermöglicht die Nutzung von Systemwerkzeugen und integrierten Funktionen zu diesem Zweck es Programmierern, Zufälligkeit und Variabilität effektiv in Skripte und Anwendungen zu integrieren.

## Wie:

Das Generieren einer Zufallszahl in Fish kann unkompliziert sein, indem man eine Kombination aus Systemwerkzeugen und Shell-Fähigkeiten verwendet. Unten sind einige Beispiele, die zeigen, wie man Zufallszahlen in bestimmten Bereichen generiert.

**Generieren einer Zufallszahl zwischen 0 und 100:**

```fish
set -l rand_num (random 0 100)
echo $rand_num
```

**Beispielausgabe:**
```fish
42
```

**Generierung einer Zufallszahl zwischen zwei beliebigen Zahlen, sagen wir 50 und 150:**

```fish
set -l min 50
set -l max 150
set -l rand_num (random $min $max)
echo $rand_num
```

**Beispielausgabe:**
```fish
103
```

**Verwendung von random zum Mischen einer Liste:**

Vielleicht möchten Sie auch Elemente in einer Liste zufällig mischen. Hier ist, wie Sie es machen können:

```fish
set -l my_list A B C D E
random (seq (count $my_list)) | while read i
    echo $my_list[$i]
end
```

**Beispielausgabe:**
```fish
C
A
E
D
B
```

Bitte beachten Sie, dass die Ausgabe jedes Mal, wenn Sie diese Befehle ausführen, aufgrund der Natur der Zufälligkeit variieren wird.

## Tiefgang

Die `random` Funktion in Fish Shell bietet eine benutzerfreundliche Schnittstelle für die Generierung von Pseudozufallszahlen. Intern nutzt es systemebene Zufallszahlengenerierungswerkzeuge, was eine portable Möglichkeit bietet, Zufälligkeit in Ihre Skripte einzuführen. Es ist jedoch wichtig zu bedenken, dass die von `random` bereitgestellte Zufälligkeit für die meisten Skriptaufgaben ausreichend ist, aber möglicherweise nicht den kryptografischen Sicherheitsanforderungen für Anwendungen genügt, die einen höheren Grad an Unvorhersehbarkeit benötigen.

Für hochsichere Kontexte erwägen Sie die Verwendung von speziellen Werkzeugen oder Programmierbibliotheken, die für kryptografische Zwecke entwickelt wurden und stärkere Zufälligkeitsgarantien bieten. Dennoch bietet die `random` Funktion von Fish Shell für allgemeines Skripting und Anwendungen, bei denen die höchsten Sicherheitsstandards für Zufälligkeit keine Anforderung sind, eine bequeme und effektive Lösung.
