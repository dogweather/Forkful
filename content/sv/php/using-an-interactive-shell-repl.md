---
title:                "Använda en interaktiv skal (REPL)"
date:                  2024-01-26T04:17:05.962961-07:00
model:                 gpt-4-0125-preview
simple_title:         "Använda en interaktiv skal (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/php/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Vad & Varför?
En interaktiv skal, eller REPL (Read-Eval-Print Loop), låter dig skriva och köra PHP-kod på flygande fot. Det är idealiskt för experiment, felsökning eller lärande, eftersom du kan testa kodsnuttar utan overhead för att skapa ett helt skript.

## Hur man gör:
Starta PHP REPL genom att köra `php -a` i din terminal. Här är ett smakprov på hur det fungerar:

```php
php > echo "Hej, världen!";
Hej, världen!
php > $arr = [1, 2, 3];
php > print_r($arr);
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
)
```

Du kan också definiera funktioner:

```php
php > function sum($a, $b) { return $a + $b; }
php > echo sum(5, 10);
15
```

## Fördjupning
REPLs har funnits i någon form sedan de tidiga dagarna av LISP på 1960-talet. PHP:s interaktiva skal är mindre avancerat jämfört med de i språk som Python eller JavaScript. Det behåller inte tillstånd mellan sessioner och saknar funktioner som autokomplettering. För en mer funktionsrik PHP REPL, överväg alternativ som `psysh` eller `boris`. Dessa tredjepartsskal erbjuder bättre verktyg för introspektion, flikkomplettering och till och med en debugger.

Under skalet fungerar PHP:s REPL genom att kompilera och exekvera varje rad kod som matas in. Begränsningarna med detta tillvägagångssätt blir tydliga med saker som att återdeklarera klasser, vilket inte är möjligt i samma session. Det är utmärkt för enkla tester men kan bli besvärligt för komplexa uppgifter.

## Se även
- [PHP-manualen - Interaktivt skal](https://www.php.net/manual/en/features.commandline.interactive.php)
- [PsySH: En körningstid utvecklarkonsol, interaktiv debugger och REPL för PHP](https://psysh.org/)
- [Boris: En liten REPL för PHP](https://github.com/borisrepl/boris)
