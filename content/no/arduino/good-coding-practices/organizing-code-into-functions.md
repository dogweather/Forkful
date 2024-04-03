---
date: 2024-01-26 01:09:02.745339-07:00
description: "\xC5 organisere koden i funksjoner betyr \xE5 dele opp koden din i gjenbrukbare\
  \ biter, hvor hver bit utf\xF8rer en spesifikk jobb. Programmerere gj\xF8r dette\
  \ for \xE5\u2026"
lastmod: '2024-03-13T22:44:41.063232-06:00'
model: gpt-4-1106-preview
summary: "\xC5 organisere koden i funksjoner betyr \xE5 dele opp koden din i gjenbrukbare\
  \ biter, hvor hver bit utf\xF8rer en spesifikk jobb."
title: Organisering av kode i funksjoner
weight: 18
---

## Hvordan:
Tenk at du vil få en LED til å blinke. Uten funksjoner, er `loop`-en din en rotete klump. Med funksjoner, er den ryddig. Her er hvordan:

```Arduino
const int LED_PIN = 13;

void setup() {
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  blinkLED(500); // Blink LED-en hver 500ms
}

// Funksjon for å få en LED til å blinke
void blinkLED(int forsinkelsestid) {
  digitalWrite(LED_PIN, HIGH);
  delay(forsinkelsestid);
  digitalWrite(LED_PIN, LOW);
  delay(forsinkelsestid);
}
```

Eksempel på output: LED-en din blinker lystig, og koden formål er klar ved første øyekast.

## Dypdykk
Før funksjoner var programmering en lineær biltur; du så hvert eneste hull fra start til slutt. Etter funksjoner, er det mer som å hoppe på flyvninger - du hopper over til de viktige delene. Historisk sett var underprogrammer (tidlige funksjoner) en revolusjon i programmering, som lot kodere unngå å gjenta seg selv – det er DRY-prinsippet, Don't Repeat Yourself (Ikke gjenta deg selv). Alternativer til funksjoner kan inkludere makroer eller bruk av klasser for objektorientert programmering (OOP). Detaljene? Når du definerer en funksjon, gir du kompilatoren en blåkopi for utførelsen av en oppgave. Med Arduino definerer du ofte void-funksjoner som fungerer som enkle kommandoer for en mikrokontroller, men funksjoner kan også returnere verdier, noe som gjør dem mer allsidige.

## Se Også
For mer om funksjoner, ta en titt på disse:

- Arduinos offisielle referanse for funksjoner: https://www.arduino.cc/reference/en/language/functions/
- Lær mer om DRY-prinsippet: https://en.wikipedia.org/wiki/Don%27t_repeat_yourself
- En oppfriskning på historien om underprogrammer: https://en.wikipedia.org/wiki/Subroutine
