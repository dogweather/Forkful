---
title:                "Stampa dell'output di debug"
date:                  2024-01-20T17:51:49.286378-07:00
model:                 gpt-4-1106-preview
simple_title:         "Stampa dell'output di debug"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/arduino/printing-debug-output.md"
---

{{< edit_this_page >}}

## What & Why? (Cosa e Perché?)
Stampare l'output di debug aiuta a seguire ciò che Arduino sta facendo e a capire problemi nel codice. Lo facciamo per testare e correggere più velocemente il nostro lavoro.

## How to: (Come fare:)
```Arduino
void setup() {
  Serial.begin(9600); // Avvia la comunicazione seriale
}

void loop() {
  Serial.println("Hello, Debug!"); // Stampa il messaggio di debug
  delay(1000); // Aspetta 1 secondo
}
```
Output:
```
Hello, Debug!
Hello, Debug!
...
```

## Deep Dive (Approfondimento)
La stampa di debug risale agli albori dell'informatica. In alternativa, si possono usare LED o display per fornire feedback visivo. L'uso di `Serial` è comodo ma richiede un cavo USB; sistemi wireless come Bluetooth o WiFi possono esser usati per debug senza fili.

## See Also (Vedi Anche)
- [La documentazione ufficiale di Arduino sulle comunicazioni Seriali](https://www.arduino.cc/reference/en/language/functions/communication/serial/)
- [Discussioni sul forum di Arduino su tecniche di debug](https://forum.arduino.cc/)