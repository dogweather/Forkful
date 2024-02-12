---
title:                "Enviando una solicitud http con autenticación básica"
date:                  2024-01-20T18:01:06.660786-07:00
model:                 gpt-4-1106-preview
simple_title:         "Enviando una solicitud http con autenticación básica"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/bash/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## ¿Qué y Por Qué?

Enviar una solicitud HTTP con autenticación básica es usar un método para acceder a un recurso en línea que requiere nombre de usuario y contraseña. Los programadores hacen esto para interactuar con APIs o servicios web que están protegidos para controlar el acceso.

## Cómo hacerlo:

Para enviar una solicitud HTTP con autenticación básica en Bash, necesitarás usar `curl` con la bandera `-u` para proporcionar las credenciales. A continuación, un ejemplo:

```Bash
# Enviar una solicitud GET con autenticación básica
usuario="tu_usuario"
contrasena="tu_contraseña"
url="http://ejemplo.com/recurso"

curl -u $usuario:$contrasena $url
```

Salida de muestra si tienes éxito:

```Bash
{"mensaje": "Acceso concedido, tus datos son..." }
```

Y si fallas, algo como esto:

```Bash
{"error": "Acceso denegado, credenciales incorrectas." }
```

Recuerda reemplazar `tu_usuario`, `tu_contraseña` y `http://ejemplo.com/recurso` con tus propias credenciales y la URL que necesitas acceder.

## Profundización

La autenticación básica HTTP es un método antiguo pero aún vigente. Fue parte de HTTP 1.0 en 1996. No es la forma más segura porque envía credenciales en texto claro, fácilmente decodificables en tránsito si no se usa HTTPS.

Alternativas incluyen OAuth y JSON Web Tokens (JWT) que proporcionan mayores niveles de seguridad. Además, algunas APIs usan parámetros de token en lugar de autenticación básica.

Cuando envías una solicitud con `curl` y autenticación básica, 'curl' codifica las credenciales en Base64 y las coloca en la cabecera de la solicitud, así:

`Authorization: Basic dHVfdXN1YXJpbzp0dV9jb250cmFzZcOxYQ==`

## Ver También

- Documentación de `curl`: https://curl.se/docs/
- Más sobre autenticación básica HTTP: https://developer.mozilla.org/es/docs/Web/HTTP/Authentication
- Alternativas seguras: sobre OAuth (https://oauth.net/2/) y JWT (https://jwt.io/).
