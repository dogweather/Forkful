---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:49.378801-07:00
description: "Obtener la fecha actual en proyectos de Arduino implica la adquisici\xF3\
  n de informaci\xF3n en tiempo real que puede ser crucial para el registro, estampado\
  \ de\u2026"
lastmod: '2024-03-13T22:44:59.343748-06:00'
model: gpt-4-0125-preview
summary: "Obtener la fecha actual en proyectos de Arduino implica la adquisici\xF3\
  n de informaci\xF3n en tiempo real que puede ser crucial para el registro, estampado\
  \ de tiempo o programaci\xF3n de tareas."
title: Obteniendo la fecha actual
weight: 29
---

## Cómo hacerlo:
Arduino por sí mismo no tiene un método incorporado para obtener directamente la fecha actual, ya que carece de un reloj en tiempo real (RTC por sus siglas en inglés). Sin embargo, esto se puede lograr utilizando módulos externos de RTC como el DS3231 y bibliotecas como `RTClib`, desarrollada por Adafruit, lo que facilita la interfaz con estos módulos.

Primero, asegúrese de que la biblioteca `RTClib` esté instalada en su Arduino IDE. A continuación, conecte su módulo RTC a su Arduino de acuerdo con su documentación.

Aquí hay un ejemplo simple para comenzar:

```cpp
#include <Wire.h>
#include "RTClib.h"

RTC_DS3231 rtc;

void setup() {
  Serial.begin(9600);

  if (!rtc.begin()) {
    Serial.println("No se pudo encontrar el RTC");
    while (1);
  }

  if (rtc.lostPower()) {
    Serial.println("El RTC perdió energía, ¡configuremos la hora!");
    // Cuando se necesita establecer la hora en un dispositivo nuevo o después de una pérdida de energía, puede hacerlo aquí.
    // rtc.adjust(DateTime(F(__DATE__), F(__TIME__)));
  }
}

void loop() {
  DateTime now = rtc.now();

  Serial.print("Fecha Actual: ");
  Serial.print(now.year(), DEC);
  Serial.print('/');
  Serial.print(now.month(), DEC);
  Serial.print('/');
  Serial.println(now.day(), DEC);

  delay(3000); // Retardo de 3 segundos para reducir el spam serial
}
```

Salida de muestra (asumiendo que su RTC ha sido previamente configurado):

```
Fecha Actual: 2023/4/15
```

Este código inicializa el módulo RTC y luego, en el loop, obtiene e imprime la fecha actual al Monitor Serial cada 3 segundos. Recuerde, la línea `rtc.adjust(...)` se puede descomentar y modificar para configurar inicialmente la fecha y hora del RTC o después de que ha perdido energía.
