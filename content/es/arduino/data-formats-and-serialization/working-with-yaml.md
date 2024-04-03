---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:41.293324-07:00
description: "YAML (YAML Ain't Markup Language) es un est\xE1ndar de serializaci\xF3\
  n de datos legible por humanos que puede ser utilizado para archivos de configuraci\xF3\
  n,\u2026"
lastmod: '2024-03-13T22:44:59.354422-06:00'
model: gpt-4-0125-preview
summary: "YAML (YAML Ain't Markup Language) es un est\xE1ndar de serializaci\xF3n\
  \ de datos legible por humanos que puede ser utilizado para archivos de configuraci\xF3\
  n, comunicaci\xF3n entre programas y almacenamiento de datos."
title: Trabajando con YAML
weight: 41
---

## Cómo hacerlo:
Trabajar directamente con YAML en Arduino no es tan sencillo como en entornos de programación de más alto nivel debido a las restricciones de memoria y la ausencia de bibliotecas nativas de procesamiento de YAML. Sin embargo, para proyectos que requieren análisis o generación de YAML, un enfoque típico implica el uso de un ordenador adicional (como una Raspberry Pi) o la conversión de archivos YAML a un formato más amigable para Arduino (como JSON) usando scripts externos. Para fines de demostración, centrémonos en este último enfoque usando una biblioteca popular: ArduinoJson.

**Paso 1:** Convierte tu configuración YAML a JSON. Puedes utilizar herramientas en línea o utilidades de línea de comandos como `yq`.

Archivo YAML (`config.yaml`):
```yaml
wifi:
  ssid: "TuSSID"
  password: "TuContraseña"
```

Convertido a JSON (`config.json`):
```json
{
  "wifi": {
    "ssid": "TuSSID",
    "password": "TuContraseña"
  }
}
```

**Paso 2:** Utiliza la biblioteca ArduinoJson para parsear el archivo JSON en tu boceto de Arduino. Primero, necesitas instalar la biblioteca ArduinoJson a través del Gestor de Bibliotecas en el Arduino IDE.

**Paso 3:** Carga y parsea el JSON en tu código. Debido a las limitaciones de almacenamiento de Arduino, imagina que la cadena JSON está almacenada en una variable o leída desde una tarjeta SD.

Boceto de Arduino de muestra:
```cpp
#include <ArduinoJson.h>

const char* jsonConfig = "{\"wifi\":{\"ssid\":\"TuSSID\",\"password\":\"TuContraseña\"}}";

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc;
  DeserializationError error = deserializeJson(doc, jsonConfig);

  if (error) {
    Serial.print(F("deserializeJson() falló: "));
    Serial.println(error.f_str());
    return;
  }

  const char* ssid = doc["wifi"]["ssid"]; // "TuSSID"
  const char* password = doc["wifi"]["password"]; // "TuContraseña"

  Serial.print("SSID: ");
  Serial.println(ssid);
  Serial.print("Contraseña: ");
  Serial.println(password);
}

void loop() {
  // Nada aquí para este ejemplo
}
```

Salida al ejecutar el boceto:
```
SSID: TuSSID
Contraseña: TuContraseña
```

Este enfoque, que implica la conversión a JSON y el aprovechamiento de la biblioteca ArduinoJson, permite un manejo manejable de la configuración YAML dentro de proyectos de Arduino, evitando el análisis directo de YAML en el microcontrolador.
