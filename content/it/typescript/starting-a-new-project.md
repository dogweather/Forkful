---
title:                "Avvio di un nuovo progetto"
date:                  2024-01-20T18:04:27.652437-07:00
model:                 gpt-4-1106-preview
simple_title:         "Avvio di un nuovo progetto"
programming_language: "TypeScript"
category:             "TypeScript"
tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/typescript/starting-a-new-project.md"
---

{{< edit_this_page >}}

## What & Why? - Cosa & Perché?
Iniziare un nuovo progetto significa creare un ambiente di lavoro da zero, dove il codice prende vita. Si fa per trasformare le idee in software funzionante, spesso per risolvere problemi specifici o esplorare nuove tecnologie.

## How to - Come fare:
```TypeScript
// Step 1: Installa TypeScript globalmente
npm install -g typescript

// Step 2: Inizia un nuovo progetto
mkdir my-new-project
cd my-new-project
npm init -y                           // crea un nuovo file package.json
tsc --init                            // genera un nuovo file tsconfig.json

// Step 3: Scrivi il tuo primo script TypeScript
echo "console.log('Ciao Mondo!');" > greeter.ts

// Step 4: Compila il tuo script
tsc greeter.ts                        // crea un nuovo file greeter.js

// Output di greeter.ts
console.log('Ciao Mondo!');
```

Per eseguire il file JavaScript risultante:

```TypeScript
node greeter.js

// Output del terminale
Ciao Mondo!
```

## Deep Dive - Un Tuffo Approfondito
TypeScript è stato creato per aggiungere tipizzazione statica a JavaScript, permettendo ai programmatori di scrivere codice più sicuro e manutenibile. Dato che JavaScript è la lingua franca del web, TypeScript offre una grande alternativa per chi cerca una maggior robustezza senza dover abbandonare l'ecosistema di JavaScript.

Prima dell'avvento di TypeScript, si usavano strumenti come JSDoc o addirittura linguaggi completamente diversi che compilano verso JavaScript, come CoffeeScript o Dart. Ogni strumento aveva i suoi vantaggi, ma TypeScript ha guadagnato popolarità grazie al suo completo appoggio da parte di Microsoft e all'integrazione con l'ambiente di sviluppo di Visual Studio Code.

Inoltre, TypeScript è altamente configurabile attraverso il file `tsconfig.json`, che gestisce il processo di compilazione. All'inizio può sembrare complesso, ma offre una granularità di controllo sulle opzioni del compilatore, consentendo di scalare il progetto dal prototipo fino alla produzione.

## See Also - Vedi Anche
- Documentazione Ufficiale TypeScript: [https://www.typescriptlang.org/docs/](https://www.typescriptlang.org/docs/)
- Tutorial TypeScript per Principianti: [https://www.typescripttutorial.net/](https://www.typescripttutorial.net/)
- tsconfig.json Documentazione ufficiale: [https://www.typescriptlang.org/tsconfig](https://www.typescriptlang.org/tsconfig)