---
title:                "Descargando una página web"
date:                  2024-01-20T17:43:21.582496-07:00
model:                 gpt-4-1106-preview
simple_title:         "Descargando una página web"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/bash/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## Qué es y por qué?
Descargar una página web significa guardar el contenido HTML en tu PC. Los programadores lo hacen para procesar la info offline, testear o automatizar tareas.

## Cómo hacerlo:
Aquí tienes ejemplos para descargar una página usando `curl` y `wget`.

```Bash
# Usando curl
curl https://example.com -o mi_pagina.html

# Usando wget
wget https://example.com
```

Output esperado: Archivos `mi_pagina.html` o `index.html` con el contenido de la página en tu directorio actual.

## Profundizando:
Antiguamente, teníamos que descargar el contenido manualmente o usar herramientas básicas de telnet para hacer peticiones HTTP. `wget` apareció en 1996, y `curl` en 1997, facilitando mucho este proceso.

### Alternativas:
Además de `curl` y `wget`, puedes usar lenguajes de scripting como Python con bibliotecas como `requests` para más control y flexibilidad.

### Detalles de implementación:
`curl` es ideal para pruebas de API y soporta múltiples protocolos. `wget` es más para descargar recursivamente. Ambos manejan redirecciones, HTTPS y autenticaciones.

## Ver también:
- [curl manual](https://curl.se/docs/manual.html)
- [wget manual](https://www.gnu.org/software/wget/manual/wget.html)
- [Guía de HTTP en MDN](https://developer.mozilla.org/es/docs/Web/HTTP)
