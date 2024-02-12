---
title:                "Obteniendo la fecha actual"
aliases:
- es/powershell/getting-the-current-date.md
date:                  2024-02-03T19:10:21.865010-07:00
model:                 gpt-4-0125-preview
simple_title:         "Obteniendo la fecha actual"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/powershell/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## ¿Qué y por qué?

Obtener la fecha actual en PowerShell trata sobre recuperar la fecha y hora actuales del sistema. Esta operación es fundamental para tareas como el registro (logging), marcación de tiempos de operaciones o hacer decisiones basadas en fechas. Los programadores usan esta capacidad para rastrear eventos, programar tareas y manejar la lógica específica de fechas en scripts y aplicaciones.

## Cómo hacerlo:

PowerShell proporciona cmdlets sencillos para obtener la fecha y la hora. El cmdlet `Get-Date` es la herramienta primaria para este propósito. Puede devolver la fecha y hora completas, que puedes formatear o manipular según tus necesidades.

```powershell
# Obtener la fecha y hora actuales
Get-Date
```

**Salida de muestra:**

```
Martes, 5 de septiembre de 2023 9:46:02 AM
```

También puedes formatear la salida para mostrar solo la información que necesitas, como solo la fecha o solo la hora.

```powershell
# Obtener solo la fecha actual en un formato específico
Get-Date -Format "yyyy-MM-dd"
```

**Salida de muestra:**

```
2023-09-05
```

```powershell
# Obtener solo la hora actual
Get-Date -Format "HH:mm:ss"
```

**Salida de muestra:**

```
09:46:02
```

### Usando la clase .NET

PowerShell permite el acceso directo a las clases .NET, ofreciendo una manera alternativa de trabajar con fechas y horas.

```powershell
# Usando la clase .NET DateTime para obtener la fecha y hora actuales
[System.DateTime]::Now
```

**Salida de muestra:**

```
Martes, 5 de septiembre de 2023 9:46:02 AM
```

Para la hora UTC:

```powershell
# Usando la clase .NET DateTime para obtener la fecha y hora UTC actuales
[System.DateTime]::UtcNow
```

**Salida de muestra:**

```
Martes, 5 de septiembre de 2023 1:46:02 PM
```

Estos comandos y clases proporcionan opciones poderosas y flexibles para trabajar con fechas y horas en PowerShell, esenciales para muchas tareas de scripting y automatización.
