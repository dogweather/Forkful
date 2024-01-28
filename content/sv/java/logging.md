---
title:                "Loggning"
date:                  2024-01-26T01:07:02.071273-07:00
model:                 gpt-4-1106-preview
simple_title:         "Loggning"
programming_language: "Java"
category:             "Java"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/java/logging.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Loggning är i grunden processen att spela in händelser som inträffar inuti en programapplikation. Programmerare loggar dessa händelser för att fånga information i körtid, felsöka problem, övervaka systemets beteende och skapa en revisionsslinga för säkerhet och efterlevnad.

## Hur man gör:
Här är ett enkelt sätt att komma igång med loggning i Java med hjälp av det inbyggda paketet `java.util.logging`.

```java
import java.util.logging.Logger;
import java.util.logging.Level;

public class AppLogging {
    private final static Logger LOGGER = Logger.getLogger(Logger.GLOBAL_LOGGER_NAME);

    public static void main(String[] args) {
        LOGGER.info("Loggar ett meddelande på INFO-nivå");

        try {
            int division = 10 / 0;
        } catch (ArithmeticException e) {
            LOGGER.log(Level.SEVERE, "Undantag inträffade", e);
        }
    }
}
```

Detta skulle producera en utskrift som liknar:

```
Jul 03, 2023 2:00:00 PM AppLogging main
INFO: Loggar ett meddelande på INFO-nivå
Jul 03, 2023 2:00:00 PM AppLogging main
SEVERE: Undantag inträffade
java.lang.ArithmeticException: / by zero
    at AppLogging.main(AppLogging.java:10)
```

## Fördjupning
Loggning i Java har utvecklats en hel del. Historiskt sett var loggningen mer ad-hoc med systemutskrifter och självskrivna mekanismer. Dock ledde behovet av standardisering till loggnings-API:er som `Log4j` och `SLF4J`. Paketet `java.util.logging` introducerades i JDK 1.4 och tillhandahöll ett standardiserat sätt att logga meddelanden.

Alternativ till `java.util.logging` (JUL) inkluderar Log4j 2 och SLF4J. Även om JUL är inbyggt i Java och därmed inte kräver ytterligare beroenden, erbjuder både Log4j 2 och SLF4J mer avancerade funktioner som mer detaljerad kontroll över loggkonfigurationen, asynkron loggning och bättre prestanda.

När det gäller implementeringen kan loggning antingen vara synkron, där varje loggmeddelande behandlas i den tråd som genererade det, eller asynkron, där meddelandena överlämnas till en separat tråd. Asynkron loggning kan förbättra prestandan men introducerar komplexitet eftersom man måste hantera samtidighetsproblem och säkerställa att loggmeddelanden inte går förlorade vid applikationskrasch.

## Se även
- [Log4j 2](https://logging.apache.org/log4j/2.x/)
- [SLF4J](http://www.slf4j.org/)
- [Oracles officiella översikt över loggning](https://docs.oracle.com/javase/8/docs/technotes/guides/logging/overview.html)
