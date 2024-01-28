---
title:                "Använda en interaktiv skal (REPL)"
date:                  2024-01-26T04:11:24.597455-07:00
model:                 gpt-4-0125-preview
simple_title:         "Använda en interaktiv skal (REPL)"
programming_language: "Bash"
category:             "Bash"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/bash/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Vad & Varför?
REPL står för Read-Eval-Print Loop, en enkel, interaktiv programmeringsmiljö. Programmerare använder den för att snabbt skriva och testa kod, experimentera med syntax och lära sig programmeringskoncept utan overheaden av att skapa och köra hela applikationer.

## Hur man gör:
I Bash är din terminal i princip en REPL. Du skriver ett kommando; den läser det, utvärderar det, skriver ut resultatet och loopar tillbaka och väntar på ditt nästa kommando. Här är ett exempel på hur du använder Bash som en REPL:

```Bash
$ echo "Hej, världen!"
Hej, världen!
$ x=$((6 * 7))
$ echo $x
42
```

Ditt inmatning följer `$ ` prompten, med utdatat som skrivs ut på nästa rad. Enkelt, eller hur?

## Fördjupning
Bash, förkortning för Bourne Again SHell, är standardshell på många Unix-baserade system. Det är en uppgradering till det ursprungliga Bourne-shellet, byggt i slutet av 1970-talet. Även om Bash är ett kraftfullt skriptverktyg, låter dess interaktiva läge dig exekvera kommandon rad för rad.

När du överväger alternativ har du Python REPL (skriv bara `python` i din terminal), Node.js (med `node`), och IPython, ett förbättrat interaktivt Python-shell. Varje språk tenderar att ha sin egen REPL-implementering.

Under ytan är REPL:er loopar som tolkar dina inmatningar (kommandon eller kod), kör dem, och returnerar resultatet till stdout (din skärm), ofta genom att använda språkets tolk direkt. Denna omedelbarhet av feedback är utmärkt för lärande och prototypning.

## Se även
- [Officiell GNU Bash-dokumentation](https://gnu.org/software/bash/manual/bash.html)
- [Learn Shell Interactive tutorial](https://www.learnshell.org/)
- [IPython Officiell Webbsida](https://ipython.org/)
- [REPL.it](https://replit.com/): En flerspråkig online REPL (Inte bara Bash!)
