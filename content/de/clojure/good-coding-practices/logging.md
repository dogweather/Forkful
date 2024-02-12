---
title:                "Protokollierung"
aliases:
- /de/clojure/logging/
date:                  2024-01-26T01:01:36.972932-07:00
model:                 gpt-4-1106-preview
simple_title:         "Protokollierung"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/clojure/logging.md"
---

{{< edit_this_page >}}

## Was & Warum?
Logging ist im Grunde das softwaretechnische Äquivalent zu einem Schiffslogbuch; es ist eine Methode, um Ereignisse aufzuzeichnen, die während des Betriebs einer Anwendung geschehen. Programmierer machen dies, um diese Ereignisse für das Debugging, die Überprüfung von Abläufen oder um Einblicke in das Verhalten eines Systems im Produktionsbetrieb zu erhalten.

## Wie geht das:
Clojure stützt sich auf die Logging-Funktionen von Java, aber Sie können diese auf eine idiomatischere Clojure-Art anzapfen. Lassen Sie uns anschauen, wie Sie `clojure.tools.logging` verwenden könnten, das eine einfache Abstraktion über mehrere Logging-Frameworks bereitstellt:

Fügen Sie zuerst eine Abhängigkeit für `clojure.tools.logging` und eine Logging-Implementierung wie `log4j` in Ihrer `project.clj` hinzu:

```clojure
:dependencies [[org.clojure/clojure "1.10.3"]
               [org.clojure/tools.logging "1.1.0"]
               [log4j/log4j "1.2.17"]]
```

Nun loggen wir einige Nachrichten:

```clojure
(require '[clojure.tools.logging :as log])

(defn compute-answer-to-everything []
  (log/debug "Beginne intensive Berechnung...")
  (Thread/sleep 3000) ; Simulation einer langen Berechnung
  (log/info "Berechnung abgeschlossen. Die Antwort ist 42.")
  42)

(compute-answer-to-everything)
```
Die Ausgabe wird standardmäßig keine `DEBUG`-Nachrichten anzeigen, da die Protokollebenen typischerweise auf `INFO` eingestellt sind:

```
INFO  [Ihr-Namespace] - Berechnung abgeschlossen. Die Antwort ist 42.
```

Sie können die Protokollebenen und Appender in einer `log4j.properties`-Datei konfigurieren, um bei Bedarf eine ausführlichere Ausgabe zu erhalten.

## Tiefergehend
`clojure.tools.logging` von Clojure gibt es schon eine Weile und dient als Brücke zwischen Clojure-Code und der Java-Logging-Welt. Historisch gesehen hat Java mehrere Iterationen und Bibliotheken für das Logging durchlaufen, wie Java's eingebaute Logging-API, `log4j`, `slf4j` und `logback`.

In Clojure, während Sie direkt Javas Logging-Frameworks nutzen können, erkennt `clojure.tools.logging` und delegiert an das Logging-Framework, das es in Ihrem Klassenpfad findet, womit Sie von einer festen Bindung an eine spezifische Implementierung entbunden sind. Dies kann dabei helfen, Ihren Clojure-Code portabler und modularer zu gestalten.

Alternativen zu `clojure.tools.logging` innerhalb des Clojure-Ökosystems sind Bibliotheken wie `timbre`, eine reine Clojure-Logging-Bibliothek mit Funktionen wie Log-Rotation, Filterung und asynchronem Logging direkt aus der Box heraus.

Implementierungsdetails sind entscheidend, wenn es um Logging in einer Multi-Thread-Umgebung wie Clojure geht. Hier bieten Unveränderlichkeit und die Verwaltung von Seiteneffekten klare Vorteile. Logging als ein Seiteneffekt sollte mit Vorsicht behandelt werden, um Leistungsengpässe zu vermeiden und Thread-Sicherheit zu gewährleisten, was die meisten Java-Logging-Frameworks bereits berücksichtigen.

Zuletzt sollten Sie strukturiertes Logging in Betracht ziehen, bei dem Logs als strukturierte Daten (wie JSON) geschrieben werden. Dies kann später für die Analyse und Verarbeitung, insbesondere bei großen, verteilten Systemen, äußerst nützlich sein.

## Siehe auch
Wenn Sie mehr wissen möchten, könnten diese Ressourcen interessant für Sie sein:

- Clojure Tools Logging Dokumentation: https://github.com/clojure/tools.logging
- Timbre, eine Clojure-Logging-Bibliothek: https://github.com/ptaoussanis/timbre
- Konfiguration von Log4J in Clojure: http://clojure-doc.org/articles/tutorials/logging_with_log4j.html
- Logback-Handbuch für fortgeschrittene Setups: http://logback.qos.ch/manual/
- Ein Leitfaden zum strukturierten Logging in Clojure: https://corfield.org/blog/2020/04/28/structured-logging/
