---
aliases:
- /es/fish-shell/sending-an-http-request/
date: 2024-01-20 17:59:43.511164-07:00
description: "Enviar una solicitud HTTP significa pedirle a un servidor web que te\
  \ brinde algo, como una p\xE1gina web o datos de una API. Los programadores lo hacen\
  \ para\u2026"
lastmod: 2024-02-18 23:09:10.449671
model: gpt-4-1106-preview
summary: "Enviar una solicitud HTTP significa pedirle a un servidor web que te brinde\
  \ algo, como una p\xE1gina web o datos de una API. Los programadores lo hacen para\u2026"
title: Enviando una solicitud http
---

{{< edit_this_page >}}

## Qué y Por Qué?
Enviar una solicitud HTTP significa pedirle a un servidor web que te brinde algo, como una página web o datos de una API. Los programadores lo hacen para interactuar con la web, probar APIs o automatizar tareas en internet.

## Cómo hacerlo:
En Fish, puedes usar `curl` o `wget` para enviar solicitudes HTTP. Aquí hay ejemplos rápidos para obtener el contenido de example.com.

```Fish Shell
curl http://example.com
```

```Fish Shell
wget -qO- http://example.com
```

La salida será el HTML de la página de inicio de example.com.

## Deep Dive
Antes, los comandos como `telnet` se usaban para interactuar con servidores web, pero eran más complicados y menos seguros. `curl` y `wget` son herramientas especializadas que soportan múltiples protocolos y métodos de encriptación. `curl` es útil para probar y depurar APIs porque te permite enviar diferentes tipos de datos y personalizar cabeceras. `wget` es excelente para descargar archivos o sitios enteros. En Fish, usar estas herramientas es sencillo, pero la potencia reside en las opciones y argumentos que permiten una amplia personalización de las solicitudes.

## Ver También
- La documentación oficial de `curl`: https://curl.se/docs/
- La documentación oficial de `wget`: https://www.gnu.org/software/wget/manual/wget.html
- Tutorial Fish Shell para principiantes: https://fishshell.com/docs/current/tutorial.html
