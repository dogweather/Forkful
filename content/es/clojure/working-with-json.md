---
title:                "Trabajando con JSON"
aliases:
- es/clojure/working-with-json.md
date:                  2024-02-03T19:22:06.989044-07:00
model:                 gpt-4-0125-preview
simple_title:         "Trabajando con JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/clojure/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Qué y Por Qué?
Trabajar con JSON (JavaScript Object Notation) en Clojure implica analizar cadenas JSON en estructuras de datos de Clojure (mapas, vectores) y viceversa. Esta tarea es fundamental para servicios web, API y aplicaciones que necesitan comunicar datos en un formato estructurado y basado en texto porque JSON es reconocido y soportado universalmente en diferentes entornos de programación.

## Cómo hacerlo:
Clojure no incluye funciones incorporadas para trabajar con JSON, por lo que típicamente se utilizan bibliotecas de terceros. `cheshire` y `jsonista` son opciones populares debido a su facilidad de uso y rendimiento.

### Usando Cheshire
Primero, agrega Cheshire a las dependencias de tu proyecto en `project.clj`:
```clj
[com.fasterxml.jackson.core/jackson-core "2.12.0"]
[cheshire "5.10.1"]
```

Para analizar una cadena JSON en un mapa de Clojure y convertir un mapa en una cadena JSON:

```clj
(require '[cheshire.core :as json])

;; Analizar cadena JSON a mapa de Clojure
(let [json-input "{\"name\":\"John\", \"age\":30}"]
  (json/parse-string json-input true)) ; => {"name" "John", "age" 30}

;; Convertir mapa de Clojure a cadena JSON
(let [clj-map {"name" "John", "age" 30}]
  (json/generate-string clj-map)) ; => "{\"name\":\"John\",\"age\":30}"
```

### Usando Jsonista
Agrega Jsonista a tu proyecto `project.clj`:
```clj
[jsonista "0.3.2"]
```

Operaciones similares con Jsonista:

```clj
(require '[jsonista.core :as j])

;; Analizar cadena JSON a Clojure
(let [json-input "{\"name\":\"Emily\", \"age\":25}"]
  (j/read-value json-input)) ; => {"name" "Emily", "age" 25}

;; Convertir mapa de Clojure a cadena JSON
(let [clj-map {"name" "Emily", "age" 25}]
  (j/write-value-as-string clj-map)) ; => "{\"name\":\"Emily\",\"age\":25}"
```

En ambas bibliotecas, tienes la opción de codificar y decodificar estructuras de datos más complejas, y hay funciones adicionales y parámetros que permiten la personalización de los procesos de serialización y deserialización. Para la mayoría de las aplicaciones, la funcionalidad demostrada proporciona una base sólida para trabajar con JSON en aplicaciones Clojure.
