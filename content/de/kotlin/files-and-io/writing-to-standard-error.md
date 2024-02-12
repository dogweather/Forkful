---
title:                "Schreiben auf Standardfehler"
aliases:
- de/kotlin/writing-to-standard-error.md
date:                  2024-02-03T19:33:46.343652-07:00
model:                 gpt-4-0125-preview
simple_title:         "Schreiben auf Standardfehler"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/kotlin/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?

Das Schreiben auf den Standardfehler (stderr) bezieht sich auf das Ausgeben von Fehlermeldungen und Diagnosen auf einem separaten Stream, abgegrenzt vom Standardausgabestream (stdout), was eine bessere Fehlerbehandlung und Protokollierung ermöglicht. Programmierer tun dies, um das Debugging zu erleichtern und sicherzustellen, dass Fehlermeldungen leicht identifiziert und bei Bedarf umgeleitet werden können, um saubere Ausgabe-Logs oder Benutzermeldungen zu erhalten.

## Wie:

In Kotlin kann das Schreiben auf stderr mit `System.err.println()` erreicht werden. Diese Methode ähnelt `System.out.println()`, leitet die Ausgabe jedoch an den Standardfehlerstrom statt an den Standardausgabestrom.

```kotlin
fun main() {
    System.err.println("Dies ist eine Fehlermeldung!")
}
```

Beispielausgabe:
```
Dies ist eine Fehlermeldung!
```

Für strukturiertere oder komplexere Anwendungen, insbesondere solche, die Protokollierungsframeworks wie Logback oder SLF4J verwenden, können Sie Logger konfigurieren, um für bestimmte Protokollebenen (z. B. ERROR) auf stderr zu schreiben.

Verwendung von SLF4J mit Logback:

1. Fügen Sie zunächst die SLF4J-API und die Logback-Implementierung zu Ihrem `build.gradle` hinzu:

```groovy
dependencies {
    implementation 'org.slf4j:slf4j-api:1.7.30'
    implementation 'ch.qos.logback:logback-classic:1.2.3'
}
```

2. Konfigurieren Sie anschließend Logback (in `src/main/resources/logback.xml`), um Fehlermeldungen auf stderr umzuleiten:

```xml
<configuration>
    <appender name="STDERR" class="ch.qos.logback.core.ConsoleAppender">
        <target>System.err</target>
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss} [%thread] %-5level %logger{36} - %msg%n</pattern>
        </encoder>
    </appender>
    
    <root level="error">
        <appender-ref ref="STDERR" />
    </root>
</configuration>
```

3. Verwenden Sie dann SLF4J in Ihrem Kotlin-Code, um Fehlermeldungen zu protokollieren:

```kotlin
import org.slf4j.LoggerFactory

fun main() {
    val logger = LoggerFactory.getLogger("ExampleLogger")
    logger.error("Dies ist eine Fehlerprotokollmeldung!")
}
```

Beispielausgabe (auf stderr):
```
2023-04-01 12:34:56 [main] ERROR ExampleLogger - Dies ist eine Fehlerprotokollmeldung!
```
