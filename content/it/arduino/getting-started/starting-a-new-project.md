---
date: 2024-01-20 18:02:45.058934-07:00
description: "Iniziare un nuovo progetto Arduino significa scrivere codice per far\
  \ interagire hardware e software. I programmatori lo fanno per creare prototipi,\u2026"
lastmod: '2024-03-13T22:44:43.684282-06:00'
model: gpt-4-1106-preview
summary: Iniziare un nuovo progetto Arduino significa scrivere codice per far interagire
  hardware e software.
title: Avvio di un nuovo progetto
weight: 1
---

## How to: (Come fare:)
```Arduino
void setup() {
  // Inizializza il pin LED come output.
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  // Accendi il LED
  digitalWrite(LED_BUILTIN, HIGH);
  // Pausa per un secondo
  delay(1000);
  // Spegni il LED
  digitalWrite(LED_BUILTIN, LOW);
  // Pausa per un secondo
  delay(1000);
}
```
Questo esempio accende e spegne il LED integrato ogni secondo.

## Deep Dive (Approfondimenti)
Arduino è nato in Italia nel 2005 per rendere l'elettronica accessibile a artisti e designer. Rispetto ad altre piattaforme come Raspberry Pi o micro:bit, Arduino brilla per la compatibilità hardware e un IDE semplificato. Spesso è la prima scelta per iniziare con l'elettronica. Il codice si scrive in C/C++ ed è strutturato in due funzioni principali: `setup()` e `loop()`. `setup()` configura una sola volta il progetto mentre `loop()` va in esecuzione ciclica. È possibile espandere la funzionalità utilizzando librerie e moduli aggiuntivi.

## See Also (Vedi Anche)
- [Sito Ufficiale di Arduino](https://www.arduino.cc/)
- [Tutorial Arduino](https://www.arduino.cc/en/Tutorial/HomePage)
- [Documentazione sul linguaggio di Arduino](https://www.arduino.cc/reference/en/)
