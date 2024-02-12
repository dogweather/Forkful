---
title:                "Trabajando con JSON"
aliases:
- /es/powershell/working-with-json/
date:                  2024-02-03T19:23:21.299917-07:00
model:                 gpt-4-0125-preview
simple_title:         "Trabajando con JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/powershell/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Qué y Por Qué?

La integración de PowerShell con JSON (JavaScript Object Notation) se trata de analizar (leer) y generar (escribir) datos JSON, un formato común para el intercambio de datos en la web. Los programadores trabajan con JSON para interactuar con APIs web, archivos de configuración, o para facilitar el intercambio de datos entre diferentes lenguajes y plataformas debido a su naturaleza liviana e independiente del lenguaje.

## Cómo hacerlo:

### Analizando JSON

Para leer o analizar JSON en PowerShell, puedes usar el cmdlet `ConvertFrom-Json`. Dada una cadena JSON, este cmdlet la convierte en un objeto de PowerShell.

```powershell
$json = '{"name": "John Doe", "age": 30, "city": "New York"}'
$person = $json | ConvertFrom-Json
$person.name
```

Salida de muestra:

```
John Doe
```

Este ejemplo demuestra cómo analizar una cadena JSON simple para acceder a las propiedades del objeto resultante.

### Generando JSON

Para generar JSON a partir de un objeto PowerShell, puedes usar el cmdlet `ConvertTo-Json`. Esto es útil para preparar datos para ser enviados a un servicio web o guardados en un archivo de configuración.

```powershell
$person = [PSCustomObject]@{
    name = "Jane Doe"
    age = 25
    city = "Los Ángeles"
}
$json = $person | ConvertTo-Json
Write-Output $json
```

Salida de muestra:

```json
{
    "name":  "Jane Doe",
    "age":  25,
    "city":  "Los Ángeles"
}
```

Este fragmento de código crea un objeto PowerShell y luego lo convierte a una cadena JSON.
