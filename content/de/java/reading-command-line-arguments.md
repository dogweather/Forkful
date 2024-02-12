---
title:                "Lesen von Kommandozeilenargumenten"
aliases:
- de/java/reading-command-line-arguments.md
date:                  2024-01-20T17:56:01.313692-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lesen von Kommandozeilenargumenten"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/java/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## What & Why?
Kommandozeilenargumente ermöglichen es Benutzern, Werte oder Verhaltensweisen einer Java-Anwendung beim Start zu steuern. Programmierer nutzen sie, um flexible und interaktive Anwendungen zu schaffen.

## How to:
```java
public class CommandLineReader {
    public static void main(String[] args) {
        if (args.length > 0) {
            System.out.println("Erhaltene Argumente:");
            for (String arg : args) {
                System.out.println(arg);
            }
        } else {
            System.out.println("Keine Argumente übergeben.");
        }
    }
}
```
Befehlszeile zum Ausführen: `java CommandLineReader Hallo Welt`
Ausgabe:
```
Erhaltene Argumente:
Hallo
Welt
```

## Deep Dive
Kommandozeilenargumente sind so alt wie die Kommandozeile selbst. In Java sind sie direkt über das `String[] args` des `main`-Verfahrens verfügbar. Alternativen zum Basis-`String[] args`-Mechanismus beinhalten die Verwendung von Bibliotheken wie Apache Commons CLI und JCommander, die das Parsen und Verwalten der Argumente vereinfachen. Wichtig beim Implementieren ist, dass diese Argumente als unveränderbare `String`-Werte vorliegen und dass die Validierung und das Parsing der Eingaben essentiell sind, um Fehlern zu vermeiden.

## See Also
- [Oracle's Java Documentation on Command-Line Arguments](https://docs.oracle.com/javase/tutorial/essential/environment/cmdLineArgs.html)
- [Apache Commons CLI](https://commons.apache.org/proper/commons-cli/)
- [JCommander Official Site](http://jcommander.org/)
