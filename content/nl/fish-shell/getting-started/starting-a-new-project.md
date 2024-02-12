---
title:                "Een nieuw project starten"
aliases:
- nl/fish-shell/starting-a-new-project.md
date:                  2024-01-28T22:08:28.764235-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een nieuw project starten"

tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/fish-shell/starting-a-new-project.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Een nieuw project starten betekent het initialiseren van een verse map met alles wat je nodig hebt om te beginnen met coderen. Programmeurs doen dit om de ontwikkeling op een schone, georganiseerde manier te starten.

## Hoe te:
```fish
# Een nieuwe map maken en erin gaan
mkdir mijn_fish_project
cd mijn_fish_project

# Een git repository initialiseren
git init

# Een initiële commit maken met een .gitignore-bestand
echo "*.log" > .gitignore
git add .gitignore
git commit -m "Initiële commit met .gitignore"

# Bonus: Stel een virtuele omgeving in indien van toepassing (niet inherent aan Fish of git)
# Zorg ervoor dat je een tool voor virtuele omgevingen hebt geïnstalleerd.
```
Voorbeelduitvoer:
```
Initialized empty Git repository in /pad/naar/mijn_fish_project/.git/
[master (root-commit) abc1234] Initiële commit met .gitignore
 1 bestand gewijzigd, 1 invoeging(+)
 create mode 100644 .gitignore
```

## Diepgaande Duik
De praktijk van het opzetten van een nieuw project heeft een lange stamboom en is meer gestandaardiseerd geworden met de opkomst van moderne versiebeheer zoals Git. Hoewel sommigen misschien de voorkeur geven aan meer grafische benaderingen, verkiezen liefhebbers van de commandoregel de fijne controle en snelheid van terminalopdrachten. Fish Shell, bekend om zijn gebruiksvriendelijke ontwerp, maakt dit eenvoudiger met handige functies zoals syntaxmarkering en automatisch aanvullen.

Alternatieven zijn het gebruik van IDE's met ingebouwde projectinitialisatie of scripts in andere shells zoals Bash of Zsh — maar Fish blinkt uit in zijn eenvoud en interactiviteit. Wat de implementatie betreft, het initialisatieproces is inherent aanpasbaar; je past het aan om te passen bij de stack en toolchain van jouw keuze. Of het nu gaat om het toevoegen van bouwgereedschappen, het instellen van linters of het creëren van een mappenstructuur, het gaat allemaal om het soepeler maken van je toekomstige ontwikkeling.

## Zie Ook
- Fish Shell Documentatie: https://fishshell.com/docs/current/index.html
- Git Basisprincipes: https://git-scm.com/book/nl/v2/Starten-met-Git-Basisprincipes
- Het opzetten van Virtuele Omgevingen: https://virtualfish.readthedocs.io/en/latest/index.html
