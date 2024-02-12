---
title:                "Anführungszeichen aus einem String entfernen"
aliases:
- /de/java/removing-quotes-from-a-string/
date:                  2024-01-26T03:39:46.651404-07:00
model:                 gpt-4-0125-preview
simple_title:         "Anführungszeichen aus einem String entfernen"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/java/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Entfernen von Anführungszeichen aus einem String bedeutet, alle Anführungszeichen – ob einfach (' '), doppelt (" ") oder beides – aus den Textdaten zu entfernen. Programmierer tun dies, um Eingaben zu bereinigen, Daten für die Speicherung vorzubereiten oder Parsing-Aufgaben zu vereinfachen, bei denen Anführungszeichen unnötig und potenziell problematisch sind.

## Wie:
Lassen Sie uns diese lästigen Anführungszeichen aus unserem Text entfernen. Wir verwenden die `replace()` Methode für die schnellen Korrekturen und regex für die harten Nüsse.

```java
public class QuoteRemover {
    public static void main(String[] args) {
        String stringWithQuotes = "\"Hallo, 'Welt'!\"";
        String withoutQuotes = stringWithQuotes.replace("\"", "").replace("'", "");
        System.out.println(withoutQuotes); // Hallo, Welt!

        // Jetzt mit regex für die Musterfans
        String stringWithMixedQuotes = "\"Java\" und 'Programmierung'";
        String cleanString = stringWithMixedQuotes.replaceAll("[\"']", "");
        System.out.println(cleanString); // Java und Programmierung
    }
}
```

## Tiefergehend
Früher waren Anführungszeichen in Strings nicht allzu lästig – Systeme waren einfacher und Daten nicht so unordentlich. Mit der Einführung komplexer Datenformate (JSON, XML) und dem Bedarf an Datenaustausch wurde die Verwaltung von Anführungszeichen entscheidend. Was Alternativen angeht, sicher, man könnte einen Parser schreiben, jeden Charakter durchlaufen und einen neuen String erstellen (könnte an einem regnerischen Tag Spaß machen). Es gibt auch Drittanbieter-Bibliotheken, die dies mit mehr Raffinesse handhaben können, indem sie Optionen zum Escapen von Zeichen anstelle deren Entfernung bieten oder verschiedene Arten von Anführungszeichen je nach Lokalisierung handhaben. Bei der Implementierung sollte man beachten, dass das Entfernen von Anführungszeichen ohne Kontext die Bedeutung oder Struktur der Daten ändern kann – man sollte immer das „Warum“ vor dem „Wie“ bedenken.

## Siehe auch
- Für einen tieferen Einblick in regex, schauen Sie sich die offiziellen Java-Dokumente an: https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Pattern.html
- Müssen Anführungszeichen escaped statt entfernt werden? Stack Overflow hilft Ihnen weiter: https://stackoverflow.com/questions/383551/escape-string-for-sql-insert
- JSON-Verarbeitung in Java? Wahrscheinlich werden Ihnen oft Anführungszeichen begegnen. Hier ist ein Ausgangspunkt: https://www.oracle.com/technical-resources/articles/java/json.html
