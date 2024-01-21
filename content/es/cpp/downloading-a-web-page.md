---
title:                "Descargando una página web"
date:                  2024-01-20T17:43:28.420987-07:00
model:                 gpt-4-1106-preview
simple_title:         "Descargando una página web"
programming_language: "C++"
category:             "C++"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/cpp/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Descargar una página web significa traer el contenido de una página de Internet a tu propia máquina. Los programadores hacen esto para analizar los datos, interactuar con servicios web, o simplemente para guardar información localmente.

## Cómo hacerlo:

```C++
#include <iostream>
#include <curl/curl.h>

static size_t WriteCallback(void *contents, size_t size, size_t nmemb, void *userp) {
    ((std::string*)userp)->append((char*)contents, size * nmemb);
    return size * nmemb;
}

int main() {
    CURL *curl;
    CURLcode res;
    std::string readBuffer;

    curl = curl_easy_init();
    if(curl) {
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com");
        curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, WriteCallback);
        curl_easy_setopt(curl, CURLOPT_WRITEDATA, &readBuffer);
        
        res = curl_easy_perform(curl);
        if(res != CURLE_OK) {
            fprintf(stderr, "curl_easy_perform() failed: %s\n", curl_easy_strerror(res));
        } else {
            std::cout << readBuffer << std::endl;
        }
        curl_easy_cleanup(curl);
    }
    return 0;
}
```

Salida de muestra:

```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
    ...
</head>
<body>
...
</body>
</html>
```

## Profundización

Históricamente, para descargar una página web se usaba `libcurl`, una biblioteca de cliente para transferir datos con URL syntax. Hoy sigue siendo una de las más usadas debido a su estabilidad y soporte en múltiples plataformas. Algunas alternativas modernas son las librerías como `Poco` y bibliotecas en otros lenguajes como Python's `requests`. Sin embargo, `libcurl` es a menudo preferida para trabajos en C++ debido a su rendimiento y flexibilidad.

`libcurl` te permite hacer mucho más que solo descargar contenido: puedes enviar datos a un servidor, modificar cabeceras HTTP, manejar cookies, y muchas otras tareas relacionadas con protocolos de red. Implementar correctamente `libcurl` requiere conocimientos de punteros y funciones de callback, pero el esfuerzo vale la pena por la potencia que ofrece. 

## Ver También

- Documentación oficial de libcurl: [curl.haxx.se/libcurl/](https://curl.haxx.se/libcurl/)
- Tutorial C++ de Curl: [https://curl.se/libcurl/c/libcurl-tutorial.html](https://curl.se/libcurl/c/libcurl-tutorial.html)
- Sobre Poco Libraries: [https://pocoproject.org/](https://pocoproject.org/)
- Libro "The C++ Standard Library" para profundizar en alternativas en C++ estándar.