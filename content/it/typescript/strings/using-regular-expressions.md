---
title:                "Utilizzo delle espressioni regolari"
aliases:
- /it/typescript/using-regular-expressions/
date:                  2024-02-03T19:18:30.708107-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilizzo delle espressioni regolari"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/typescript/using-regular-expressions.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa & Perché?
Le espressioni regolari, o regex, rappresentano uno strumento potente per la ricerca e il confronto di pattern nella programmazione. I programmatori utilizzano le regex per compiti come la validazione dell'input dell'utente, la ricerca nel testo o la manipolazione delle stringhe perché sono efficienti e versatili.

## Come fare:

Vediamo come si utilizza regex in TypeScript per le attività comuni.

```TypeScript
// Definire un pattern regex per un indirizzo email
const emailPattern = /\S+@\S+\.\S+/;

// Verificare se una stringa corrisponde al pattern dell'email
const email = "user@example.com";
console.log(emailPattern.test(email)); // Output: vero

// Trovare e sostituire i numeri in una stringa
const replaceDigits = "Item 25 costs $30".replace(/\d+/g, '#');
console.log(replaceDigits); // Output: "Item # costs $#"

// Estrarre parti specifiche da una stringa usando i gruppi di cattura
const data = "April 10, 2021";
const datePattern = /(\w+) (\d+), (\d+)/;
const [, month, day, year] = datePattern.exec(data) || [];
console.log(month, day, year); // Output: "April" "10" "2021"
```

## Approfondimento

Negli anni '50, il matematico Stephen Kleene descrisse le espressioni regolari come un modello per rappresentare linguaggi regolari, che in seguito divenne fondamentale nell'informatica. Oggi, le regex sono onnipresenti nella programmazione per gestire il testo.

Sebbene le regex siano un coltellino svizzero per le operazioni sulle stringhe, non sono prive di alternative. A seconda della complessità del compito, a volte i metodi delle stringhe come `includes()`, `startsWith()`, `endsWith()`, o persino l'analisi con una libreria possono essere migliori. Ad esempio, analizzare una stringa JSON complessa usando regex può essere un incubo—utilizzare invece un parser JSON.

Riguardo all'implementazione, le regex in JavaScript e TypeScript si basano sulla specifica del linguaggio ECMAScript. Internamente, i motori usano macchine a stati per corrispondere ai pattern in modo efficiente. È importante notare che le operazioni con regex possono diventare costose in termini di prestazioni, specialmente con pattern scritti male—attenzione al "catastrophic backtracking".

## Vedi Anche

- MDN Web Docs sulle Espressioni Regolari: [MDN Espressioni Regolari](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
- Regex101: Uno strumento per testare e mettere a punto i pattern regex [Regex101](https://regex101.com/)
- "Mastering Regular Expressions" libro per una comprensione approfondita: [O'Reilly](https://www.oreilly.com/library/view/mastering-regular-expressions/0596528124/)
