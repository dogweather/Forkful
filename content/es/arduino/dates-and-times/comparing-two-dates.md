---
title:                "Comparación de dos fechas"
aliases:
- es/arduino/comparing-two-dates.md
date:                  2024-01-20T17:32:16.930960-07:00
model:                 gpt-4-1106-preview
simple_title:         "Comparación de dos fechas"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/arduino/comparing-two-dates.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Comparar dos fechas es verificar si una es anterior, posterior o igual a la otra. Programadores lo hacen para eventos, registros temporales o para medir periodos de tiempo.

## Cómo hacerlo:
```Arduino
#include <TimeLib.h>

void setup() {
  Serial.begin(9600);
  // Inicializar con dos fechas de ejemplo: Año, Mes, Día
  tmElements_t fecha1 = {0, 0, 0, 15, 3, 2023 - 1970}; // 15 marzo 2023
  tmElements_t fecha2 = {0, 0, 0, 18, 3, 2023 - 1970}; // 18 marzo 2023
  
  time_t tiempo1 = makeTime(fecha1);
  time_t tiempo2 = makeTime(fecha2);
  
  if(tiempo1 < tiempo2) {
      Serial.println("Fecha1 es anterior a Fecha2");
  } else if (tiempo1 > tiempo2) {
      Serial.println("Fecha1 es posterior a Fecha2");
  } else {
      Serial.println("Ambas fechas son iguales");
  }
}

void loop() {
  // Este código solo necesita ejecutarse una vez
}
```
Salida de ejemplo:
```
Fecha1 es anterior a Fecha2
```

## Profundización
Comparar fechas en programación no es nuevo. Viene desde los principios de la computación. En Arduino, se hace uso de la biblioteca TimeLib para manejo de fechas y tiempo. 

Una alternativa sería emplear la estructura `RTClib` si estamos trabajando con un módulo RTC (Real Time Clock).

Los detalles de implementación varían según la precisión requerida y si se incluye la hora además de la fecha. Comparar fechas toma relevancia para funciones como alarmas, registros de eventos y temporizadores.

## Ver También
- Documentación de la biblioteca TimeLib: https://www.pjrc.com/teensy/td_libs_Time.html
- Información sobre módulos RTC y su uso en Arduino: https://www.arduino.cc/en/Reference/RTC
- Comparación de tiempos en C++ (base para programación Arduino): http://www.cplusplus.com/reference/ctime/difftime/
