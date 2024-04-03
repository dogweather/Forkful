---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:59:03.996018-07:00
description: "Il logging nello sviluppo software \xE8 il processo di registrazione\
  \ di informazioni sull'esecuzione di un programma, progettato per tracciare il suo\u2026"
lastmod: '2024-03-13T22:44:42.915365-06:00'
model: gpt-4-0125-preview
summary: "Il logging nello sviluppo software \xE8 il processo di registrazione di\
  \ informazioni sull'esecuzione di un programma, progettato per tracciare il suo\
  \ comportamento e diagnosticare problemi."
title: Registro degli Eventi
weight: 17
---

## Come fare:
In Go, il logging può essere implementato utilizzando il pacchetto della libreria standard `log`. Questo pacchetto fornisce capacità di logging semplici, come la scrittura su output standard o su file. Cominciamo con un esempio basico di logging su output standard:

```go
package main

import (
	"log"
)

func main() {
	log.Println("Questa è una voce di log di base.")
}
```

Output:
```
2009/11/10 23:00:00 Questa è una voce di log di base.
```

Il timestamp all'inizio della voce di log viene aggiunto automaticamente dal pacchetto `log`. Successivamente, esploriamo come fare il log su un file invece che sull'output standard:

```go
package main

import (
	"log"
	"os"
)

func main() {
	file, err := os.OpenFile("app.log", os.O_CREATE|os.O_APPEND|os.O_WRONLY, 0666)
	if err != nil {
		log.Fatal(err)
	}
	defer file.Close()

	log.SetOutput(file)
	log.Println("Questa voce di log va su un file.")
}
```

Ora, implementiamo un caso d'uso più avanzato: personalizzare il formato del log. Go ti consente di creare un logger personalizzato con `log.New()`:

```go
package main

import (
	"log"
	"os"
)

func main() {
	logger := log.New(os.Stdout, "LOG PERSONALIZZATO: ", log.Ldate|log.Ltime|log.Lshortfile)
	logger.Println("Questo è un messaggio di log personalizzato.")
}
```

Output:
```
LOG PERSONALIZZATO: 2009/11/10 23:00:00 main.go:11: Questo è un messaggio di log personalizzato.
```

Questo esempio prefissa ogni messaggio di log con "LOG PERSONALIZZATO: " e include la data, l'ora e la posizione del file sorgente.

## Approfondimento
Il pacchetto `log` della libreria standard di Go è semplice e sufficiente per molte applicazioni, ma manca di alcune delle funzionalità più sofisticate trovate nelle librerie di logging di terze parti, come il logging strutturato, la rotazione dei log e il logging basato sui livelli. Pacchetti come `zap` e `logrus` offrono queste funzionalità avanzate e sono ben considerati nella comunità di Go per la loro performance e flessibilità.

Il logging strutturato, ad esempio, ti permette di registrare dati in un formato strutturato (come JSON), che è particolarmente utile per le applicazioni moderne basate sul cloud dove i log potrebbero essere analizzati da vari strumenti o servizi. `zap`, in particolare, è noto per la sua alta performance e il basso sovraccarico di allocazione, rendendolo adatto per applicazioni dove velocità ed efficienza sono critiche.

Storicamente, il logging in Go è evoluto significativamente dall'inizio del linguaggio. Le prime versioni di Go fornivano le capacità di logging di base che vediamo nel pacchetto `log`. Tuttavia, man mano che il linguaggio cresceva in popolarità e la complessità delle applicazioni scritte in Go aumentava, la comunità ha iniziato a sviluppare librerie di logging più sofisticate per soddisfare le loro esigenze. Oggi, mentre il pacchetto `log` standard rimane un'opzione valida per applicazioni semplici, molti sviluppatori si rivolgono a queste soluzioni di terze parti per esigenze di logging più complesse.
