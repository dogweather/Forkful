---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:57:12.289093-07:00
description: "Generar n\xFAmeros aleatorios en programaci\xF3n se trata de crear una\
  \ secuencia de n\xFAmeros que no se pueden predecir razonablemente mejor que por\
  \ casualidad.\u2026"
lastmod: '2024-03-13T22:44:58.462664-06:00'
model: gpt-4-0125-preview
summary: "Generar n\xFAmeros aleatorios en programaci\xF3n se trata de crear una secuencia\
  \ de n\xFAmeros que no se pueden predecir razonablemente mejor que por casualidad."
title: "Generando n\xFAmeros aleatorios"
weight: 12
---

## Cómo hacerlo:
En Go, los números aleatorios se generan utilizando el paquete `math/rand` para números pseudoaleatorios o `crypto/rand` para números pseudoaleatorios criptográficamente seguros. Vamos a explorar ambos.

### Usando `math/rand` para Números Pseudoaleatorios
Primero, importe el paquete `math/rand` y el paquete `time` para sembrar el generador. Sembrar asegura que obtenga una secuencia diferente de números en cada ejecución.

```go
package main

import (
	"fmt"
	"math/rand"
	"time"
)

func main() {
	rand.Seed(time.Now().UnixNano())
	fmt.Println("Un número aleatorio:", rand.Intn(100)) // Genera un número entre 0 y 99
}
```

Salida de muestra: `Un número aleatorio: 42`

### Usando `crypto/rand` para Números Pseudoaleatorios Criptográficamente Seguros
Para aplicaciones más sensibles a la seguridad, el paquete `crypto/rand` es adecuado ya que genera números aleatorios difíciles de predecir, lo que los hace adecuados para operaciones criptográficas.

```go
package main

import (
	"crypto/rand"
	"fmt"
	"math/big"
)

func main() {
	n, _ := rand.Int(rand.Reader, big.NewInt(100))
	fmt.Println("Un número aleatorio seguro:", n)
}
```

Salida de muestra: `Un número aleatorio seguro: 81`

## Análisis Profundo
La diferencia central entre los paquetes `math/rand` y `crypto/rand` en Go proviene de su fuente de entropía y sus casos de uso intencionados. `math/rand` genera números pseudoaleatorios basados en una semilla inicial; por lo tanto, la secuencia es determinista y se puede predecir si se conoce la semilla. Esto es adecuado para escenarios donde el rendimiento alto y no la imprevisibilidad absoluta es la preocupación clave, como simulaciones o juegos.

Por otro lado, `crypto/rand` deriva la aleatoriedad del sistema operativo subyacente, lo que lo hace adecuado para usos criptográficos donde la imprevisibilidad es crucial. Sin embargo, esto tiene el costo de rendimiento y complejidad en el manejo de los números que genera (como tratar con el tipo `*big.Int` para enteros).

Históricamente, la noción de generación de números aleatorios en las computadoras siempre ha bailado en el borde de la verdadera "aleatoriedad", con sistemas tempranos que dependían en gran medida de algoritmos deterministas que imitaban la aleatoriedad. A medida que las computadoras evolucionaron, también lo hicieron estos algoritmos, incorporando fuentes de entropía más sofisticadas de sus ambientes.

A pesar de estos avances, la búsqueda de la perfección en la aleatoriedad en la informática es inherentemente paradójica, dada la naturaleza determinista de las computadoras mismas. Es por esto que, para la mayoría de aplicaciones donde la previsibilidad sería perjudicial, los números pseudoaleatorios criptográficamente seguros de fuentes como `crypto/rand` son la mejor alternativa, a pesar de su sobrecarga.

En esencia, el enfoque de Go con dos paquetes distintos para la generación de números aleatorios aborda elegantemente los compromisos entre el rendimiento y la seguridad, permitiendo a los desarrolladores elegir basándose en sus necesidades específicas.
