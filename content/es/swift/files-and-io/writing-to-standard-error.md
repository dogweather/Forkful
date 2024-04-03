---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:44.309535-07:00
description: "Escribir en el error est\xE1ndar (stderr) se trata de dirigir los mensajes\
  \ de error o de diagn\xF3stico de tu programa a un flujo separado, distinto del\
  \ salida\u2026"
lastmod: '2024-03-13T22:44:59.432691-06:00'
model: gpt-4-0125-preview
summary: "Escribir en el error est\xE1ndar (stderr) se trata de dirigir los mensajes\
  \ de error o de diagn\xF3stico de tu programa a un flujo separado, distinto del\
  \ salida est\xE1ndar (stdout)."
title: "Escribiendo en el error est\xE1ndar"
weight: 25
---

## Cómo hacerlo:
En Swift, escribir en el error estándar se puede hacer usando la clase `FileHandle` para un acceso directo al stderr. Aquí hay un ejemplo simple:

```swift
import Foundation

// Definir un mensaje
let errorMessage = "Ocurrió un error.\n"

// Convertir el mensaje a datos
if let data = errorMessage.data(using: .utf8) {
    // Escribir el mensaje de error en stderr
    FileHandle.standardError.write(data)
}
```

Salida a stderr (típicamente vista en una consola o terminal):
```
Ocurrió un error.
```

Para registros más complejos o cuando se trabaja con bibliotecas externas, se podría considerar el uso de una biblioteca de terceros como **SwiftLog**. Aunque **SwiftLog** no escribe en stderr directamente de manera predeterminada, puedes implementar un backend de registro personalizado para lograrlo. He aquí un ejemplo simplificado de cómo definir un manejador de registro personalizado que escribe en stderr:

Primero, añade **SwiftLog** a las dependencias de tu proyecto en `Package.swift`:
```swift
// swift-tools-version:5.3

import PackageDescription

let package = Package(
    name: "TuNombreDePaquete",
    dependencies: [
        .package(url: "https://github.com/apple/swift-log.git", from: "1.0.0"),
    ],
    targets: [
        .target(
            name: "TuNombreDeDestino",
            dependencies: [
                .product(name: "Logging", package: "swift-log"),
            ]),
    ]
)
```

Luego, implementa un manejador de registro personalizado que escribe en stderr:

```swift
import Logging
import Foundation

struct StderrLogHandler: LogHandler {
    let label: String
    
    var logLevel: Logger.Level = .info
    
    func log(level: Logger.Level, message: Logger.Message, metadata: Logger.Metadata?, source: String, file: String, function: String, line: UInt) {
        let output = "\(message)\n"
        if let data = output.data(using: .utf8) {
            FileHandle.standardError.write(data)
        }
    }
    
    subscript(metadataKey metadataKey: String) -> Logger.Metadata.Value? {
        get { return nil }
        set(newValue) { }
    }
    
    var metadata: Logger.Metadata {
        get { return [:] }
        set(newMetadata) { }
    }
}

// Uso
LoggingSystem.bootstrap(StderrLogHandler.init)
let logger = Logger(label: "com.example.tuapp")

logger.error("Este es un mensaje de error")
```

Salida a stderr:
```
Este es un mensaje de error
```

Este manejador personalizado te permite dirigir tus mensajes de error de SwiftLog directamente al error estándar, integrándose de forma transparente con otros mensajes de registro que tu aplicación pueda generar.
