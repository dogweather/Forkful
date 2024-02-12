---
title:                "Bruke et interaktivt skall (REPL)"
date:                  2024-01-26T04:14:12.058858-07:00
model:                 gpt-4-0125-preview
simple_title:         "Bruke et interaktivt skall (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/fish-shell/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
REPL, eller Les-Evaluer-Skriv-Løkke, er et interaktivt programmeringsmiljø som tar enkelt brukerinput, utfører dem, og returnerer resultatet. Programmerere bruker det for umiddelbar tilbakemelding, feilsøking, og rask eksperimentering med programmeringskonsepter uten overheaden av å kompilere og kjøre et fullstendig program.

## Hvordan:
I Fish er den interaktive skallet standardmodus når du starter det. Slik ser det ut i aksjon:

```Fish Shell
> set color blue
> echo "Himmelen er $color"
Himmelen er blå
```

Du kan også kjøre innebygde funksjoner og leke deg med kommandosubstitusjoner:

```Fish Shell
> function cheer
      echo "Heia Fish $argv!"
  end
> cheer Kodere
Heia Fish Kodere!
```

Ikke bare definere funksjoner, du kan utføre kodebiter på-the-fly og se output umiddelbart:

```Fish Shell
> math "40 / 2"
20
```

## Dyp Dykk
Konseptet med REPL går langt tilbake til Lisp programmeringsspråket på 1960-tallet. Denne formen for interaktiv programmering satte standarden for miljøer som Python's `ipython` og Ruby's `irb`. Fish fortsetter trenden med fokus på brukervennlighet og interaktiv bruk.

Fish skiller seg fra andre skall som Bash ved at den er designet med interaktivitet i tankene fra starten. Den tilbyr syntaksutheving, autoforslag og tab kompletteringer som gjør den kraftig å bruke i en REPL-stil arbeidsflyt. Enda bedre, kommandoene dine huskes og er søkbare, noe som gjør gjentatte tester en bris.

Alternativer til Fishs REPL kan være `bash` eller `zsh` når de er parret med utvidelser som `bash-completion` eller `oh-my-zsh`, men Fish tilbyr en rikere opplevelse rett ut av boksen.

## Se Også:
- Fish Dokumentasjon: https://fishshell.com/docs/current/index.html
- En interessant sammenligning av Fish vs. andre skall: https://www.slant.co/versus/2209/3686/~fish_vs_bash
- En dypere dykk inn i REPLs: https://en.wikipedia.org/wiki/Read–eval–print_loop
- Interaktiv programmering i Lisp, et historisk blikk: http://www.paulgraham.com/ilisp.html
