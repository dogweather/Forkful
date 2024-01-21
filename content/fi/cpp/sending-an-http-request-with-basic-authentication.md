---
title:                "HTTP-pyynnön lähettäminen perusautentikoinnilla"
date:                  2024-01-20T18:01:03.439862-07:00
model:                 gpt-4-1106-preview
simple_title:         "HTTP-pyynnön lähettäminen perusautentikoinnilla"
programming_language: "C++"
category:             "C++"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/cpp/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why?

Lähetämme HTTP-pyyntöjä perusautentikoinnilla liittääksemme käyttäjätunnus-salasanapari verkkopalveluihin. Tämä on vakiomenetelmä suojattujen resurssien käyttöoikeuden hallintaan.

## How to:

```C++
#include <iostream>
#include <curl/curl.h>
#include <string>

static size_t data_write(void* buf, size_t size, size_t nmemb, void* userp) {
    if(userp) {
        std::ostream& os = *static_cast<std::ostream*>(userp);
        std::streamsize len = size * nmemb;
        if(os.write(static_cast<char*>(buf), len))
            return len;
    }

    return 0;
}

CURL* curl = curl_easy_init();

if(curl) {
    std::string response_string;
    std::string header_string;
    curl_easy_setopt(curl, CURLOPT_URL, "http://your-protected-resource.com");

    // Set the Authorization header with basic authentication credentials
    curl_easy_setopt(curl, CURLOPT_HTTPAUTH, (long)CURLAUTH_BASIC);
    curl_easy_setopt(curl, CURLOPT_USERNAME, "username");
    curl_easy_setopt(curl, CURLOPT_PASSWORD, "password");

    curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, data_write);
    curl_easy_setopt(curl, CURLOPT_WRITEDATA, &response_string);
    curl_easy_setopt(curl, CURLOPT_HEADERDATA, &header_string);

    CURLcode res = curl_easy_perform(curl);
    if(res != CURLE_OK) {
        fprintf(stderr, "curl_easy_perform() failed: %s\n", curl_easy_strerror(res));
    } else {
        std::cout << "Response from server: " << response_string << std::endl;
    }

    curl_easy_cleanup(curl);
}
```

Output:

```
Response from server: { "message": "Hello, world!" }
```

## Deep Dive

HTTP Basic Authentication on vanhin verkkotunnistusmenetelmä. Sen käyttö on yksinkertaista: käyttäjätunnus ja salasana yhdistetään, koodataan Base64-koodauksella ja lähetetään `Authorization`-otsakkeessa. Historiallisesti, tämä oli helppo tapa suojata resursseja, mutta nykyään se ei ole parhaita käytäntöjä, koska perustiedot lähetetään tekstimuodossa, joka on helposti dekoodattavissa.

Vaihtoehtoja perusautentikoinnille ovat OAuth, API-avaimet ja JWT-tunnukset. Näistä kukin tarjoaa eri tason turvallisuutta ja mukautuvuutta. Käyttäessäsi cURL-kirjastoa C++:lla, voit mukauttaa otsakkeita tarpeen mukaan erilaisten autentikointimenetelmien tueksi.

CURL on monipuolinen kirjasto HTTP-verkkopyyntöjen tekemiseen. Se käsittelee monia verkkosovellusten kehittämisen yksityiskohtia, kuten protokollatuki ja autentikointimekanismit, poistaen monimutkaisuutta suorasta ohjelmoinnista.

## See Also

- cURL documentation: https://curl.se/libcurl/
- 'Base64' encoding explained: https://en.wikipedia.org/wiki/Base64
- Understanding HTTP Basic Authentication: https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication 
- C++ Network Programming with Boost.Asio: https://www.boost.org/doc/libs/1_75_0/doc/html/boost_asio.html