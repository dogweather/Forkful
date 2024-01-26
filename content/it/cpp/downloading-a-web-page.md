---
title:                "Scaricare una pagina web"
date:                  2024-01-20T17:43:43.937391-07:00
model:                 gpt-4-1106-preview
simple_title:         "Scaricare una pagina web"
programming_language: "C++"
category:             "C++"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/cpp/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (Cosa e Perché?)
Scaricare una pagina web significa raccogliere dati da Internet direttamente nel tuo programma. I programmatori lo fanno per analizzare contenuti, raccogliere dati o interagire con servizi online.

## How to: (Come fare:)
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

    curl_global_init(CURL_GLOBAL_DEFAULT);
    curl = curl_easy_init();

    if(curl) {
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com");
        curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, WriteCallback);
        curl_easy_setopt(curl, CURLOPT_WRITEDATA, &readBuffer);

        res = curl_easy_perform(curl);
        if(res != CURLE_OK)
            std::cerr << "curl_easy_perform() failed: " << curl_easy_strerror(res) << std::endl;

        std::cout << readBuffer << std::endl;
        
        curl_easy_cleanup(curl);
    }

    curl_global_cleanup();
    return 0;
}
```
Questo pezzo di codice utilizza libcurl per scaricare il contenuto di "http://example.com" e stamparlo sullo standard output.

## Deep Dive (Nel Profondo)
Historicamente, scaricare dati dalla rete nella programmazione C++ ha richiesto una varietà di librerie perché il linguaggio standard non ha questa funzionalità. libcurl è una scelta popolare, ma esistono alternative come Boost.Asio o Poco. Ognuna ha un approccio e sintassi diversi. libcurl è considerata user-friendly con supporto a molteplici protocolli oltre HTTP/HTTPS, come FTP, SMTP, e altro. È importante gestire gli errori di rete e fare pulizia nell'uso della libreria per evitare memory leak.

## See Also (Vedi Anche)
- Documentazione ufficiale di libcurl: https://curl.se/libcurl/
- Tutorial Curl con esempi di codice: https://curl.se/libcurl/c/example.html
- Documentazione di Boost.Asio: https://www.boost.org/doc/libs/release/libs/asio/
- Guida Poco Libraries: https://pocoproject.org/docs/
