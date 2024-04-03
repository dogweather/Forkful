---
date: 2024-01-26 00:59:18.755393-07:00
description: "\"Logging\" significa mantenere un registro degli eventi, delle transazioni\
  \ o delle attivit\xE0 che si verificano nel tempo in un sistema. I programmatori\
  \ lo\u2026"
lastmod: '2024-03-13T22:44:43.688923-06:00'
model: gpt-4-1106-preview
summary: "\"Logging\" significa mantenere un registro degli eventi, delle transazioni\
  \ o delle attivit\xE0 che si verificano nel tempo in un sistema."
title: Registrazione Eventi (Logging)
weight: 17
---

## Come fare:
Arduino non dispone di una libreria di logging integrata come alcuni altri ambienti, ma è possibile implementare un logging di base sulla console Seriale con poco sforzo. Ecco un esempio rapido per iniziare:

```arduino
void setup() {
  // Avvia la comunicazione seriale con il dato baud rate
  Serial.begin(9600);

  // Attendi il collegamento della porta seriale - necessario solo su alcune schede
  while (!Serial) {
    ; // attendi che la porta seriale si colleghi. Necessario per USB nativo
  }

  // Registra un messaggio informativo che indica che il processo di configurazione è completo
  Serial.println("Configurazione completata!");
}

void loop() {
  // Logger semplice che stampa il tempo di attività ogni secondo
  static unsigned long lastLogTime = 0;
  unsigned long currentMillis = millis();

  if (currentMillis - lastLogTime >= 1000) {
    lastLogTime = currentMillis;
    Serial.print("Tempo di attività (ms): ");
    Serial.println(currentMillis);

    // Qui potresti anche aggiungere log di errore, avvertimenti o altre informazioni.
  }
  
  // Resto della logica del tuo programma qui...
}
```

Esempio di output Seriale:
```
Configurazione completata!
Tempo di attività (ms): 1000
Tempo di attività (ms): 2000
Tempo di attività (ms): 3000
...
```

## Approfondimento:
Storicamente, il logging sui microcontrollori non era semplice come su un sistema operativo completo. Risorse limitate significavano che ogni byte contava e gli sviluppatori dovevano fare attenzione a non intasare il sistema. Con l'avvento di schede più capaci e la semplificazione del processo da parte della piattaforma Arduino, il logging è diventato più accessibile.

Anche se il codice sopra dimostra il logging tramite l'interfaccia Seriale, altri metodi includono la scrittura su una scheda SD, l'invio di dati tramite rete a un server remoto o persino l'uscita su un piccolo LCD.

Implementare un sistema di logging comporta considerazioni come la rotazione, la gravità dei livelli (info, debug, avviso, errore) e l'impatto sulle prestazioni. Su un Arduino, potrebbe essere necessario prestare attenzione alle limitazioni di memoria durante il logging di strutture dati complesse. Per il logging remoto, la sicurezza dei log trasmessi è anche una preoccupazione.

Soluzioni più sofisticate come Syslog, uno standard di logging ampiamente adottato, esistono al di fuori del mondo Arduino, ma è possibile integrare librerie di terze parti che offrono funzionalità simili con vari gradi di complessità e requisiti di risorse.

## Vedi anche:
- [Riferimento `Serial` di Arduino](https://www.arduino.cc/reference/en/language/functions/communication/serial/)
- [Logging su scheda SD con Arduino](https://www.arduino.cc/en/Tutorial/LibraryExamples/Datalogger)
- [SparkFun Data Logging shield](https://www.sparkfun.com/products/13712)
- [TinyWeb: Un esempio pratico di logging remoto con Arduino](https://www.arduino.cc/en/Tutorial/WebClientRepeating)
