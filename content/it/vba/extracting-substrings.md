---
title:                "Estrazione di sottostringhe"
aliases:
- it/vba/extracting-substrings.md
date:                  2024-02-01T21:53:09.362745-07:00
model:                 gpt-4-0125-preview
simple_title:         "Estrazione di sottostringhe"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/vba/extracting-substrings.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa & Perché?

L'estrazione di sottostringhe in Visual Basic for Applications (VBA) implica l'isolamento di parti specifiche di una stringa in base a criteri dati. I programmatori fanno ciò per compiti come l'analisi dei dati, la validazione e la formattazione, dove è cruciale manipolare ed estrarre informazioni dai dati testuali.

## Come fare:

In VBA, si usano principalmente le funzioni `Mid`, `Left` e `Right` per estrarre sottostringhe. Di seguito, esploriamo queste funzioni con esempi:

1. **Mid**: Estrae una sottostringa da una stringa a partire da una posizione specificata.
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Mid(exampleString, 7, 5)
   Debug.Print result  ' Output: World
   ```

2. **Left**: Estrae una sottostringa dalla parte sinistra della stringa, fino a un numero specificato di caratteri.
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Left(exampleString, 5)
   Debug.Print result  ' Output: Hello
   ```

3. **Right**: Estrae una sottostringa dalla parte destra della stringa, fino a un numero specificato di caratteri.
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Right(exampleString, 5)
   Debug.Print result  ' Output: World
   ```

Queste funzioni fondamentali costituiscono il fondamento dell'estrazione di sottostringhe in VBA, offrendo approcci robusti e semplici alla manipolazione delle stringhe.

## Approfondimento:

Storicamente, la capacità di manipolare le stringhe nella programmazione è stata essenziale, con BASIC (il progenitore di VBA) tra i primi a democratizzare questa capacità nei primi giorni del personal computing. Le funzioni `Mid`, `Left` e `Right` in VBA ereditano questo retaggio, offrendo un'interfaccia semplificata per i programmatori moderni.

Sebbene queste funzioni siano abbastanza efficaci per molti compiti, l'emergere delle Espressioni Regolari nei linguaggi più recenti ha fornito un modo più potente e flessibile per lavorare con il testo. Nonostante ciò, la semplicità immediata e la disponibilità delle funzioni tradizionali di sottostringa di VBA le rendono perfettamente adatte per compiti rapidi e per chi è nuovo alla programmazione.

Per operazioni di parsing e ricerca più complesse all'interno delle stringhe, VBA supporta anche il matching di pattern tramite l'operatore `Like` e le Espressioni Regolari tramite l'oggetto `VBScript.RegExp`, anche se questi richiedono un po' più di configurazione e comprensione per essere utilizzati efficacemente. Mentre questi strumenti offrono maggiore potenza, la natura diretta di `Mid`, `Left` e `Right` ne garantisce la continua rilevanza e utilità in molti programmi VBA.
