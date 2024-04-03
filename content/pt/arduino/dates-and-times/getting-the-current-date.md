---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:49.355621-07:00
description: "Obter a data atual em projetos Arduino envolve a obten\xE7\xE3o de informa\xE7\
  \xF5es em tempo real que podem ser cruciais para registro, marca\xE7\xE3o de tempo\
  \ ou\u2026"
lastmod: '2024-03-13T22:44:46.849253-06:00'
model: gpt-4-0125-preview
summary: "Obter a data atual em projetos Arduino envolve a obten\xE7\xE3o de informa\xE7\
  \xF5es em tempo real que podem ser cruciais para registro, marca\xE7\xE3o de tempo\
  \ ou agendamento de tarefas."
title: Obtendo a data atual
weight: 29
---

## Como fazer:
O próprio Arduino não possui um método embutido para buscar diretamente a data atual, pois ele não tem um relógio de tempo real (RTC). Porém, isso pode ser alcançado usando módulos RTC externos, como o DS3231, e bibliotecas como a `RTClib`, desenvolvida pela Adafruit, que tornam a interface com esses módulos simples.

Primeiro, certifique-se de que a biblioteca `RTClib` está instalada no seu Arduino IDE. Depois, conecte o seu módulo RTC ao seu Arduino de acordo com a documentação dele.

Aqui está um exemplo simples para começar:

```cpp
#include <Wire.h>
#include "RTClib.h"

RTC_DS3231 rtc;

void setup() {
  Serial.begin(9600);

  if (!rtc.begin()) {
    Serial.println("Não foi possível encontrar o RTC");
    while (1);
  }

  if (rtc.lostPower()) {
    Serial.println("RTC perdeu energia, vamos ajustar a hora!");
    // Quando a hora precisa ser ajustada em um novo dispositivo ou após a perda de energia, você pode fazer isso aqui.
    // rtc.adjust(DateTime(F(__DATE__), F(__TIME__)));
  }
}

void loop() {
  DateTime now = rtc.now();

  Serial.print("Data Atual: ");
  Serial.print(now.year(), DEC);
  Serial.print('/');
  Serial.print(now.month(), DEC);
  Serial.print('/');
  Serial.println(now.day(), DEC);

  delay(3000); // Atraso de 3 segundos para reduzir o spam serial
}
```

Saída de amostra (assumindo que seu RTC foi previamente ajustado):

```
Data Atual: 2023/4/15
```

Este código inicializa o módulo RTC e, então, no loop, busca e imprime a data atual no Monitor Serial a cada 3 segundos. Lembre-se, a linha `rtc.adjust(...)` pode ser descomentada e modificada para ajustar inicialmente a data e a hora do RTC ou após ele ter perdido energia.
