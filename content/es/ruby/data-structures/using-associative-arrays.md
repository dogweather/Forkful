---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:12:26.302449-07:00
description: "Los arreglos asociativos, m\xE1s conocidos como hashes en Ruby, permiten\
  \ emparejar claves \xFAnicas con valores. Son indispensables cuando necesitas llevar\
  \ un\u2026"
lastmod: '2024-03-13T22:44:59.582722-06:00'
model: gpt-4-0125-preview
summary: "Los arreglos asociativos, m\xE1s conocidos como hashes en Ruby, permiten\
  \ emparejar claves \xFAnicas con valores."
title: Uso de matrices asociativas
weight: 15
---

## Cómo hacerlo:
Crear y usar hashes en Ruby es sencillo. Puedes inicializar un hash vacío, llenarlo con pares clave-valor, acceder a los valores por sus claves y más. Así es cómo se hace:

```Ruby
# Creando un hash
my_hash = { "name" => "John Doe", "age" => 30 }

# Otra manera de crear un hash
another_hash = Hash.new
another_hash["position"] = "Desarrollador"

# Accediendo los valores del hash
puts my_hash["name"] # Salida: John Doe

# Añadiendo un nuevo par clave-valor
my_hash["language"] = "Ruby"
puts my_hash # Salida: {"name"=>"John Doe", "age"=>30, "language"=>"Ruby"}

# Iterando a través de un hash
my_hash.each do |key, value|
  puts "#{key}: #{value}"
end
# Salida:
# name: John Doe
# age: 30
# language: Ruby
```

También puedes usar símbolos como claves más eficientes:

```Ruby
# Usando símbolos para las claves
symbol_hash = { name: "Jane Doe", age: 22 }
puts symbol_hash[:name] # Salida: Jane Doe
```

## Estudio Profundo:
El concepto de arreglos asociativos no es único de Ruby; muchos lenguajes los implementan bajo varios nombres, como diccionarios en Python u objetos en JavaScript (cuando se usan como pares clave-valor). En las etapas iniciales de Ruby, los hashes eran algo más lentos y no tan versátiles. Sin embargo, con el tiempo, la implementación de hashes en Ruby se ha optimizado mucho, especialmente para claves de símbolos, haciéndolos extremadamente eficientes para accesos y actualizaciones frecuentes.

Los hashes de Ruby se destacan por su facilidad de uso sintáctico y flexibilidad: puedes usar casi cualquier tipo de objeto como clave, aunque los símbolos y las cadenas son los más comunes. Internamente, los hashes de Ruby están implementados usando un algoritmo de hashing que equilibra la velocidad y la eficiencia de memoria, incluso a medida que el número de elementos escala.

Aunque los hashes son increíblemente versátiles, no son la solución total para el almacenamiento de datos en Ruby. Para colecciones ordenadas, los arreglos son más apropiados, y para conjuntos de elementos únicos, un Set podría ser una mejor opción. Además, para estructuras de datos muy complejas, podría ser aconsejable crear clases personalizadas.

Recuerda, la elección de usar un hash frente a otras estructuras de datos depende en gran medida del caso de uso específico: los hashes sobresalen en búsquedas rápidas y en mantener asociaciones entre claves únicas y sus valores.
