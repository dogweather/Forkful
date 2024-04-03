---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:31:26.328063-07:00
description: "Escribir pruebas en PowerShell implica crear scripts que validen autom\xE1\
  ticamente la funcionalidad de tu c\xF3digo de PowerShell, asegur\xE1ndose de que\
  \ se\u2026"
lastmod: '2024-03-13T22:44:59.295779-06:00'
model: gpt-4-0125-preview
summary: "Escribir pruebas en PowerShell implica crear scripts que validen autom\xE1\
  ticamente la funcionalidad de tu c\xF3digo de PowerShell, asegur\xE1ndose de que\
  \ se comporte como se espera."
title: Escribiendo pruebas
weight: 36
---

## Cómo hacerlo:
PowerShell no tiene un marco de pruebas incorporado, pero Pester, un módulo de terceros muy popular, es ampliamente utilizado para escribir y ejecutar pruebas. Así es como comenzar con Pester para probar tus funciones de PowerShell.

Primero, instala Pester si aún no lo has hecho:

```powershell
Install-Module -Name Pester -Scope CurrentUser -Force
```

Luego, considera que tienes una simple función de PowerShell que quieres probar, guardada como `MyFunction.ps1`:

```powershell
function Get-MultipliedNumber {
    param (
        [int]$Number,
        [int]$Multiplier = 2
    )

    return $Number * $Multiplier
}
```

Para probar esta función con Pester, crea un script de prueba llamado `MyFunction.Tests.ps1`. En este script, usa los bloques `Describe` e `It` de Pester para definir los casos de prueba:

```powershell
# Importar la función a probar
. .\MyFunction.ps1

Describe "Pruebas de Get-MultipliedNumber" {
    It "Multiplica el número por 2 cuando no se proporciona multiplicador" {
        $result = Get-MultipliedNumber -Number 3
        $result | Should -Be 6
    }

    It "Multiplica correctamente el número por el multiplicador dado" {
        $result = Get-MultipliedNumber -Number 3 -Multiplier 3
        $result | Should -Be 9
    }
}
```

Para ejecutar las pruebas, abre PowerShell, navega al directorio que contiene tu script de prueba y utiliza el comando `Invoke-Pester`:

```powershell
Invoke-Pester .\MyFunction.Tests.ps1
```

La salida de muestra se verá así, indicando si tus pruebas pasaron o fallaron:

```
Starting discovery in 1 files.
Discovery finished in 152ms.
[+] C:\ruta\a\MyFunction.Tests.ps1 204ms (182ms|16ms)
Tests completed in 204ms
Tests Passed: 2, Failed: 0, Skipped: 0 NotRun: 0
```

Esta salida muestra que ambas pruebas han pasado, dándote confianza en que tu función `Get-MultipliedNumber` se comporta como se espera bajo los escenarios que has probado.
