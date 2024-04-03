---
date: 2024-01-20 18:00:33.811078-07:00
description: "Mandar una solicitud HTTP es el proceso de pedir o enviar datos a un\
  \ servidor web. Lo hacemos para interactuar con APIs, obtener recursos, enviar\u2026"
lastmod: '2024-03-13T22:44:58.797224-06:00'
model: gpt-4-1106-preview
summary: Mandar una solicitud HTTP es el proceso de pedir o enviar datos a un servidor
  web.
title: Enviando una solicitud http
weight: 44
---

## How to:
Para mandar una solicitud HTTP, vamos a usar `fetch`, que está ya incluido en JavaScript y es accesible en TypeScript.

```TypeScript
// GET Request
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => response.json())
  .then(data => console.log(data));

// POST Request
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then(response => response.json())
  .then(json => console.log(json));

```
Esto imprimiría en consola la respuesta del servidor en formato JSON.

## Deep Dive
La función `fetch` se introdujo en la web para reemplazar `XMLHttpRequest`, que era más compleja y menos intuitiva. Si necesitas compatibilidad con navegadores antiguos, podrías considerar herramientas como `axios` o `jQuery.ajax`. Además, con TypeScript, es buena idea definir interfaces para las respuestas que esperas, lo que te ayuda a manejar los datos de forma predecible y segura.

## See Also
- [MDN Web Docs - Fetch API](https://developer.mozilla.org/es/docs/Web/API/Fetch_API)
- [TypeScript Handbook - Utility Types](https://www.typescriptlang.org/docs/handbook/utility-types.html)
- [JSONPlaceholder - Fake Online REST API](https://jsonplaceholder.typicode.com/)
