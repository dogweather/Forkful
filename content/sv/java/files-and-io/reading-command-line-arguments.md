---
title:                "Läsa in kommandoradsargument"
aliases:
- /sv/java/reading-command-line-arguments/
date:                  2024-01-20T17:56:21.282050-07:00
model:                 gpt-4-1106-preview
simple_title:         "Läsa in kommandoradsargument"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/java/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## Vad & Varför?

Kommandoradsargument låter dig mata in data till ditt Java-program när du startar det. Programmerare använder detta för att göra programmen flexibla och dynamiska utan att behöva ändra koden inuti.

## Hur gör man:

Enkelt! I din `main`-metod, de där `String[] args` är dina argument. Kika här:

```java
public class CommandLineExample {
    public static void main(String[] args) {
        if (args.length > 0) {
            System.out.println("Hej, " + args[0] + "!");
        } else {
            System.out.println("Hej, främling!");
        }
    }
}
```

Kör den så här och se magin:

```
$ java CommandLineExample Världen
Hej, Världen!
```

```java
$ java CommandLineExample
Hej, främling!
```

## Fördjupning

Kommandoradsargument har varit med länge, sedan första dagarna av programmering. Det är ett simpelt sätt att skicka information till programmet. 

I moderna system kan alternativ som miljövariabler eller konfigurationsfiler vara bättre för komplexa data. Men ärligt talat? För snabb och smutsig input, slår inget att kunna skicka argument direkt.

När du läser argumenten, tänk på att de alltid är `String`. Vill du ha något annat, som `int`, måste du konvertera det själv. Var också medveten om index: de startar på 0.

## Se även

- [The Java™ Tutorials – Command Line Arguments](https://docs.oracle.com/javase/tutorial/essential/environment/cmdLineArgs.html)
- [Apache Commons CLI](https://commons.apache.org/proper/commons-cli/) för att hantera komplicerade kommandoradsscenarion.
