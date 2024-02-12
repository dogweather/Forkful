---
title:                "Convirtiendo una fecha en una cadena de texto"
aliases:
- /es/python/converting-a-date-into-a-string/
date:                  2024-01-20T17:37:28.867053-07:00
model:                 gpt-4-1106-preview
simple_title:         "Convirtiendo una fecha en una cadena de texto"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/python/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Convertir una fecha a texto significa transformar un objeto `datetime` en Python a un formato de cadena de caracteres (string). Esto se hace para facilitar la visualización, almacenamiento o para integrarlo en formatos que lo requieren, como JSON o CSV.

## Cómo se hace:
Vamos directo al grano. Aquí tienes un ejemplo de cómo convertir una fecha en cadena:

```Python
from datetime import datetime

# Crear un objeto datetime
fecha_actual = datetime.now()

# Convertirlo a string
fecha_como_cadena = fecha_actual.strftime('%d/%m/%Y %H:%M:%S')

print(fecha_como_cadena)  # muestra algo como '31/03/2023 16:45:23'
```

El método `strftime` permite especificar el formato deseado para la fecha. Aquí `%d` es el día, `%m` es el mes, `%Y` es el año con siglo, `%H` es la hora en formato 24 horas, `%M` son los minutos y `%S` los segundos.

## Buceo Profundo
Históricamente, los humanos siempre hemos necesitado registrar fechas y tiempos, y la informática no es la excepción. En Python, la manipulación de fechas y tiempos se hace a través de la librería `datetime`, que se incluyó en la versión 2.3.

Existen alternativas al método `strftime`, como usar la funcionalidad de f-strings (formateo de cadenas literales) introducida en Python 3.6, pero `strftime` sigue siendo relevante por su flexibilidad y precisión en el formateo. 

Respecto a los detalles de implementación, `strftime` toma el objeto `datetime` y a través del patrón de formato que le pasamos, devuelve una representación en cadena. Cada secuencia de formatos, como `%Y` corresponde a componentes específicos de la fecha y hora.

## Ver También
Aquí tienes enlaces a fuentes relacionadas para aprender más:

- [Documentación de datetime - Python](https://docs.python.org/3/library/datetime.html)
- [Tutorial de strftime y strptime](https://strftime.org/)
- [PEP 498 -- Literal String Interpolation](https://www.python.org/dev/peps/pep-0498/)
- [w3schools Python DateTime](https://www.w3schools.com/python/python_datetime.asp)
