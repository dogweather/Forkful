---
title:                "Convirtiendo una fecha en una cadena de texto"
date:                  2024-03-08T21:53:31.766794-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## ¿Qué y por qué?

Convertir una fecha en una cadena en Dart es una tarea común cuando necesitas mostrar información de fecha y hora en un formato legible por humanos, o cuando tienes la intención de serializar datos para almacenamiento o transmisión. Este proceso permite la fácil representación y manipulación de valores de fecha y hora en un formato que es comprensible y puede ser personalizado dependiendo del caso de uso.

## Cómo hacerlo:

Dart proporciona la clase `DateTime` para manejar fechas y horas, y el paquete `intl` para formatear. Primero, asegúrate de tener el paquete `intl` agregando `intl: ^0.17.0` (o la última versión) a tu archivo `pubspec.yaml`.

### Usando la Biblioteca Central de Dart

```dart
DateTime now = DateTime.now();
String formattedDate = "${now.year}-${now.month}-${now.day}";
print(formattedDate); // Salida: 2023-4-12 (por ejemplo, esto depende de la fecha actual)
```

Este ejemplo construye directamente una cadena a partir de las propiedades de `DateTime`.

### Usando el paquete `intl`

Primero, importa el paquete:

```dart
import 'package:intl/intl.dart';
```

Luego, formatea la fecha:

```dart
DateTime now = DateTime.now();
String formattedDate = DateFormat('yyyy-MM-dd').format(now);
print(formattedDate); // Salida: 2023-04-12
```

El paquete `intl` permite un formateo mucho más complejo fácilmente, incluyendo formatos específicos de la localidad:

```dart
String formattedDateLocale = DateFormat.yMMMMd('en_US').format(now);
print(formattedDateLocale); // Salida: April 12, 2023
```

Estos ejemplos muestran formas simples pero poderosas de convertir y formatear fechas en cadenas en Dart, ya sea utilizando la funcionalidad central de Dart o utilizando el paquete `intl` para opciones de formateo más avanzadas.
